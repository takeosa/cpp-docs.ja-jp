---
title: "コンパイラ エラー C2969 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2969
dev_langs:
- C++
helpviewer_keywords:
- C2969
ms.assetid: e4ea3d66-b937-4b2c-b42a-96e03fb11579
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fbb6606e3e0b6a007574dde7ec1f012cbb49a841
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2969"></a>コンパイラ エラー C2969
構文エラー: 'symbol': メンバー関数の定義を終了するための '}' がありません。  
  
 テンプレート メンバー関数の定義内に一致しないかっこがあります。  
  
 次の例では C2969 が生成されます。  
  
```  
// C2969.cpp  
// compile with: /c  
class A {  
   int i;  
public:  
   A(int i) {}  
};  
  
A anA(1);  
  
class B {  
   A a;  
   B() : a(anA);   // C2969  
   // try the following line instead  
   // B() : a(anA) {}  
};  
```
