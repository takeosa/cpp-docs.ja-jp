---
title: "コンパイラ エラー C2807 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2807
dev_langs: C++
helpviewer_keywords: C2807
ms.assetid: bd7a207a-f379-4de6-8ee8-c7cab78b3480
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5fbea2518dabf2851ff6d620095c898f7a2a35c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2807"></a>コンパイラ エラー C2807
後置 'operator 演算子' を 2 番目の仮パラメーターは 'int' である必要があります。  
  
 後置演算子を 2 番目のパラメーターには、間違った型があります。  
  
 次の例では、C2807 が生成されます。  
  
```  
// C2807.cpp  
// compile with: /c  
class X {  
public:  
   X operator++ ( X );   // C2807 nonvoid parameter  
   X operator++ ( int );   // OK, int parameter  
};  
```