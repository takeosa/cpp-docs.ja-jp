---
title: "コンパイラ エラー C2255 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2255
dev_langs: C++
helpviewer_keywords: C2255
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d5f3c3487afa522f19b9db34146d3d467f9ab40a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2255"></a>コンパイラ エラー C2255
'element' : クラス定義外では使用できません  
  
 たとえば、非メンバー関数が `friend`として宣言されているとします。  
  
 次の例では、C2255 が生成されます。  
  
```  
// C2255.cpp  
// compile with: /c  
class A {  
private:  
   void func1();  
   friend void func2();  
};  
  
friend void func1() {}   // C2255  
void func2(){}  
```