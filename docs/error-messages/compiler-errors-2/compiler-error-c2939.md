---
title: "コンパイラ エラー C2939 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2939
dev_langs:
- C++
helpviewer_keywords:
- C2939
ms.assetid: 455b050b-f2dc-4b5b-bd6a-e1f81d3d1644
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fbe4bb402755f421996edabfb9dffb43edf65228
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2939"></a>コンパイラ エラー C2939
'class': type-class-id が、ローカル データ変数として再定義されています  
  
 ジェネリック クラスまたはテンプレート クラスをローカル データ変数として使用することはできません。  
  
 このエラーは、中かっこが正しく一致していない場合に発生することがあります。  
  
 次の例では C2939 が生成されます。  
  
```  
// C2939.cpp  
template<class T>  
struct TC { };   
int main() {  
   int TC<int>;   // C2939  
   int TC;   // OK  
}  
```  
  
 C2939 は、ジェネリックを使用する場合にも発生することがあります。  
  
```  
// C2939b.cpp  
// compile with: /clr  
generic<class T>  
ref struct GC { };  
  
int main() {  
   int GC<int>;   // C2939  
   int GC;   // OK  
}  
```
