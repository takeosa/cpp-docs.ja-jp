---
title: "コンパイラ エラー C3033 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3033
dev_langs:
- C++
helpviewer_keywords:
- C3033
ms.assetid: 8628b6bb-a650-4ed2-af13-57acd2f7ddbb
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c005874c7a11f5ec250daa42f8857070bbfad8dc
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3033"></a>コンパイラ エラー C3033
'var': 'clause' 句の変数は const 宣言された型を含むことはできません  
  
 特定の句に渡された値を `const` 変数にすることはできません。  
  
 次の例では C3033 が生成されます。  
  
```  
// C3033.cpp  
// compile with: /openmp /link vcomps.lib  
int main() {  
   const int val = 1;  
   int val2 = 1;  
  
   #pragma omp parallel reduction(+ : val)   // C3033  
   ;  
  
   #pragma omp parallel reduction(+ : val2)   // OK  
   ;  
}  
```
