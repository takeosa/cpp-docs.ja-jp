---
title: "コンパイラ エラー C3754 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3754
dev_langs:
- C++
helpviewer_keywords:
- C3754
ms.assetid: 14b877bc-9277-40ec-af1c-196a58b45f10
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 01fe6b5568da2e55d5ade4eca22a84ea4a0041e7
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3754"></a>コンパイラ エラー C3754
delegate コンス トラクター: メンバー関数 'function' は型 'type' のインスタンスで呼び出すことはできません  
  
 関数を含まない型へのポインターを使用して関数呼び出しが行われました。  
  
## <a name="example"></a>例  
 次の例では、C3754 が生成されます。  
  
```  
// C3754a.cpp  
// compile with: /clr  
using namespace System;  
  
delegate void MyDel();  
  
interface class MyInterface {};  
  
ref struct MyClass : MyInterface {  
   void f() {}  
};  
  
int main() {  
   MyInterface^ p = gcnew MyClass;  
   MyDel^ q = gcnew MyDel(p, &MyClass::f);   // C3754  
   // try the following line instead  
//   MyDel^ q = gcnew MyDel(safe_cast<MyClass^>(p), &MyClass::f);  
}  
```  

