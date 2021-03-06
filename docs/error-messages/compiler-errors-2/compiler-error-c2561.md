---
title: "コンパイラ エラー C2561 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2561
dev_langs: C++
helpviewer_keywords: C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ce30ffb454deb7bc847e736458295d037826a0ad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2561"></a>コンパイラ エラー C2561
'identifier': 関数が値を返す必要があります  
  
 関数は、値を返すとして宣言されていますが、関数定義が含まれない、`return`ステートメントです。  
  
 このエラーは、無効な関数プロトタイプによって発生することができます。  
  
1.  関数が値を返さない場合は、戻り値の型と関数を宣言[void](../../cpp/void-cpp.md)です。  
  
2.  関数のすべての分岐がプロトタイプで宣言された型の値を返すことを確認してください。  
  
3.  C++ の関数の戻り値を格納するインライン アセンブリ ルーチンを含む、`AX`レジスタは、return ステートメントを必要があります。 値をコピー`AX`を一時変数に、関数からその変数を返すとします。  
  
 次の例では、C2561 が生成されます。  
  
```  
// C2561.cpp  
int Test(int x) {  
   if (x) {  
      return;   // C2561  
      // try the following line instead  
      // return 1;  
   }  
   return 0;  
}  
  
int main() {  
   Test(1);  
}  
```