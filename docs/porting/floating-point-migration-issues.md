---
title: "浮動小数点の移行に関する問題 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 36a1b552-2f2b-4919-bc9d-c17f42434954
caps.latest.revision: 1
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 6b30a331ca93d704539d32d003333f4f0a2823fb
ms.openlocfilehash: b84e3edcba95e75b877e0acf2651d3d1a9ac8816
ms.lasthandoff: 02/28/2017

---
# <a name="floating-point-migration-issues"></a>浮動小数点の移行に関する問題  
  
新しいバージョンの Visual Studio にプロジェクトをアップグレードすると、特定の浮動小数点演算の結果が変わることがあります。 これは一般的に、利用できるプロセッサをより効果的に活用するためにコード生成が変更されたか、C ランタイム ライブラリ (CRT) の数学関数で使用されるアルゴリズムが修正または変更されたことにより発生します。 一般的に、言語標準で指定される制限内では、新しい結果が正しくなります。 後続のセクションでは、変更内容と以前の関数結果を得る方法を紹介します。重要と思われる場合は参考にしてください。  

## <a name="new-math-functions-and-universal-crt-changes"></a>新しい数学関数とユニバーサル CRT の変更  
  
Visual Studio ではこの数年間でほとんどの CRT 数学関数が利用可能になりましたが、Visual Studio 2013 からは、ISO C99 で必要なすべての関数が含まれています。 これらの関数は、正確性とパフォーマンスのバランスをとるために実装されます。 あらゆるケースで正確に丸めた結果を生成するには非常にコストがかかる場合があるため、正確に丸めた結果の近似値を効率的に生成できるように当該関数が設計されました。 ほとんどのケースでは、生成される結果は正確に丸めた結果の +/-&1; *ulp* (最終桁単位) の誤差範囲内に収まります。ただし、不正確さがそれより大きくなる場合もあります。 以前に別の数学ライブラリを利用してこれらの関数を得ていた場合、実装方法の違いが結果の違いとして現れる可能性があります。   
    
Visual Studio 2015 で数学関数がユニバーサル CRT に移行されたとき、新しいアルゴリズムがいくつか使用されました。Visual Studio 2013 で新しく導入された関数の実装にあったバグが修正されました。 このような変更がこれらの関数を使用する浮動小数点計算の結果の違いとなって現れた可能性があります。 バグ問題のあった関数は、erf、exp2、remainder、remquo、scalbln、scalbn、とその float バリアントと long double バリアントでした。  Visual Studio 2015 のその他の変更により、_clear87、_clearfp、fegetenv、fesetenv、feholdexcept 関数の浮動小数点のステータス ワードと例外状態情報の保存における問題が修正されました。  
  
## <a name="processor-differences-and-compiler-flags"></a>プロセッサの違いとコンパイラ フラグ  
  
浮動小数点数値演算ライブラリ関数の多くは、CPU アーキテクチャの種類に応じて実装の種類も異なります。 たとえば、32 ビット x86 CRT の実装は、64 ビット x64 CRT の実装とは異なります。 さらに、関数の中には特定の CPU アーキテクチャに対して複数の実装が用意されているものもあります。 CPU でサポートされている命令セットに応じて実行時に動的に実装を選択するのが最も効率的な方法です。 たとえば、32 ビット x86 CRT で、一部の関数には x87 実装と SSE2 実装の両方が用意されています。 SSE2 をサポートしている CPU で実行すると、速い方の SSE2 実装が使用されます。 SSE2 をサポートしていない CPU で実行すると、遅い方の x87 実装が使用されます。 これは古いコードを移行したときに表示されることがあります。既定の x86 コンパイラ アーキテクチャ オプションが Visual Studio 2012 で [/arch:SSE2](../build/reference/arch-x86.md) に変更されたためです。 数値演算ライブラリ関数の実装の種類が異なると、結果を生成するために使用する CPU 命令およびアルゴリズムも異なる場合があります。このため、異なるプラットフォームで関数の生成する結果が異なる場合があります。 ほとんどの場合、結果は正確に丸めた結果の +/-&1; ulp の誤差範囲内に収まります。ただし、実際の結果は、CPU 間で異なる場合があります。  
  
Visual Studio のさまざまな浮動小数点モードでコード生成が修正されたことが、古いコードを新しいコードと比較したときの浮動小数点演算の結果にも影響を与える可能性があります。同じコンパイラ フラグを使用する場合にもそれが当てはまります。 たとえば、[/fp:precise](../build/reference/fp-specify-floating-point-behavior.md) (既定) または **/fp:strict** を指定して Visual Studio 2010 で生成したコードは、中間の not-a-number (NaN) 値を式で正しく伝えていない可能性があります。 そのため、以前のコンパイラで数値結果を出していた一部の式が今では NaN 結果を正しく生成していることが考えられます。 **/fp:fast** に対して有効になっているコード最適化がプロセッサの機能をより効果的に活用できるようになったことで違いが現れることもあります。 このような最適化では、指示が少なくなっていても、生成される結果に影響が現れていることがあります。以前は表示されていた中間演算がなくなったためです。  
  
## <a name="how-to-get-identical-results"></a>同じ結果を得る方法  
  
ほとんどの場合、最新のコンパイラとライブラリの浮動小数点の変更により、動作がより早くなったか、またはより正確になりました。あるいはこの両方を満たすようになりました。 SSE2 指示が x87 指示に取って代わると、プロセッサ パワーのパフォーマンスが改善されることがあります。 ただし、以前のコンパイラの浮動小数点動作を正確に複製しなければならないコードがある場合、Visual Studio のネイティブ マルチターゲット機能を利用し、影響を受けるプロジェクトを以前のツールセットで構築することを検討してください。 詳細については、「[Visual Studio でネイティブ マルチ ターゲットを利用し、古いプロジェクトを作成する](use-native-multi-targeting.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
  
[旧バージョンの Visual C++ からのプロジェクトのアップグレード](upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
[アップグレードに関する潜在的な問題 (Visual C++) の概要](overview-of-potential-upgrade-issues-visual-cpp.md)  
[2003 から 2015 の Visual C++ の履歴の変更](visual-cpp-change-history-2003-2015.md)  
