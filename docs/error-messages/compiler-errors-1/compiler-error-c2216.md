---
title: "コンパイラ エラー C2216 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2216
dev_langs: C++
helpviewer_keywords: C2216
ms.assetid: 250f6bdc-a5e1-495f-a1e8-6e8e7021ad9d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a7a8bf9b012ec0479b763b6e5a31e5e28a4995e0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2216"></a>コンパイラ エラー C2216
'keyword1' は 'keyword2' と共に使用できません  
  
 相互に排他的である 2 つのキーワードが共に使用されました。  
  
## <a name="example"></a>例  
 次の例では C2216 が生成されます。  
  
```  
// C2216.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal  
   static int staticConst2 = 10;   // C2216  
};  
```  
  
## <a name="example"></a>例  
 次の例では C2216 が生成されます。  
  
```  
// C2216b.cpp  
// compile with: /clr /c  
public ref class X {  
   extern property int i { int get(); }   // C2216 extern not allowed on property  
   typedef property int i2;   // C2216 typedef not allowed on property  
};  
```  
  
## <a name="example"></a>例  
 次の例では C2216 が生成されます。  
  
```  
// C2216c.cpp  
// compile with: /clr /c  
public interface struct I {  
   double f();  
   double g();  
   double h();  
};  
  
public ref struct R : I {  
   virtual double f() new override { return 0.0; }   // C2216  
   virtual double g() new { return 0.0; }   // OK  
   virtual double h() override { return 0.0; }   // OK  
};  
```