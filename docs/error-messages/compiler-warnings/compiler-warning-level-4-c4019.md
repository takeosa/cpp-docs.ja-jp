---
title: "コンパイラの警告 (レベル 4) C4019 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4019
dev_langs:
- C++
helpviewer_keywords:
- C4019
ms.assetid: 4ecfe85d-673f-4334-8154-36fe7f0b3444
caps.latest.revision: 6
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
ms.openlocfilehash: 746514d855e3bedf033ce67a860043b03f30924a
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4019"></a>コンパイラの警告 (レベル 4) C4019
グローバル スコープで空行があります。  
  
 グローバル スコープのセミコロンの前にステートメントがありません。  
  
 この警告は、余分なセミコロンを削除すると解決される場合があります。  
  
## <a name="example"></a>例  
  
```  
// C4019.c  
// compile with: /Za /W4  
#define declint( varname ) int varname;  
declint( a );   // C4019, int a;;  
declint( b )   // OK, int b;  
  
int main()  
{  
}  
```
