---
title: "コンパイラ エラー C2611 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2611
dev_langs: C++
helpviewer_keywords: C2611
ms.assetid: 3f2d5253-f24f-4724-83d0-6b2aa6a4e551
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6741ce6f8d951670f44e45191d8b3658cc1c5317
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2611"></a>コンパイラ エラー C2611
'token': 無効な次 ' ~' (識別子が必要です)  
  
 トークンは、識別子ではありません。  
  
 次の例では、C2611 が生成されます。  
  
```  
// C2611.cpp  
// compile with: /c  
class C {  
   C::~operator int();   // C2611  
   ~C();   // OK  
};  
```