---
title: "致命的なエラー C1004 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1004
dev_langs:
- C++
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c6a9e74d7918e1cb2c9190c87f4f1ec75f89237b
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1004"></a>致命的なエラー C1004
予期しないファイルの終わりが見つかりました  
  
 コンパイラでは、コンストラクトを解決せず、ソース ファイルの末尾に達しました。 コードがない、次の要素のいずれか。  
  
-   右かっこ  
  
-   右かっこ  
  
-   終了のコメント マーカー (*/)  
  
-   セミコロン  
  
 このエラーを解決するには、次を確認します。  
  
-   既定のディスク ドライブは、ソース ファイルと 2 倍の空き領域に関する必要な一時ファイルは、十分なスペースがします。  
  
-   `#if`終了を false に評価されるディレクティブ`#endif`ディレクティブです。  
  
-   キャリッジ リターンとライン フィードを使用して、ソース ファイルは終了しません。  
  
 次の例では、C1004 が生成されます。  
  
```  
// C1004.cpp  
#if TEST  
int main() {}  
// C1004  
```  
  
 考えられる解決策:  
  
```  
// C1004b.cpp  
#if TEST  
#endif  
  
int main() {}  
```
