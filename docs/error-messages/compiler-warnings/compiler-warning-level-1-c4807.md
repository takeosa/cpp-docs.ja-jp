---
title: "コンパイラの警告 (レベル 1) C4807 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4807
dev_langs:
- C++
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 1548905fd242707c1cdf01c2cbc51b5c9e50cfce
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4807"></a>コンパイラの警告 (レベル 1) C4807
'operation': 'type' 型と 'type' 型の符号付きビットフィールドの混用は安全ではありません。  
  
 この警告は、1 ビットの符号付きビットフィールドと `bool` 変数を比較すると、生成されます。 1 ビットの符号付きビットフィールドには、値 -1 または 0 のみを含めることがでるため、 `bool`と比較するのは危険です。 `bool` と 1 ビットの符号なしビットフィールドは `bool` を同じであり、0 または 1 のみを保持できるため、これらを混用しても警告は生成されません。  
  
## <a name="example"></a>例  
 次の例では C4807 が生成されます。  
  
```  
// C4807.cpp  
// compile with: /W1  
typedef struct bitfield {  
   signed mybit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bool b = true;  
  
   // try..  
   // int b = true;  
  
   bf.mybit = -1;  
   if (b == bf.mybit) {   // C4807  
      b = false;  
   }  
}  
```
