---
title: "インライン アセンブリでの C++ 関数の呼び出し |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0c91829eac3247255d8fe3cb966a61fca5319f94
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="calling-c-functions-in-inline-assembly"></a>インライン アセンブリでの C++ 関数の呼び出し
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 `__asm`ブロックがないオーバー ロードされるグローバルの C++ 関数のみを呼び出すことができます。 オーバー ロードされたグローバル C++ 関数、または C++ メンバー関数を呼び出した場合、コンパイラ エラーが発生します。  
  
 宣言された任意の関数を呼び出すこともできます**extern"C"**リンケージ。 これにより、`__asm`ブロック内にすべての標準ヘッダー ファイルがライブラリ関数を宣言するために、C のライブラリ関数を呼び出し、C プログラム**extern"C"**リンケージ。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)