---
title: "コンパイラ エラー C3131 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3131
dev_langs:
- C++
helpviewer_keywords:
- C3131
ms.assetid: 38f20fac-83c9-4cd9-b7b5-74ca8f650ea6
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 53b42516687d34b7eeb92ee46becf9afa99ef592
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3131"></a>コンパイラ エラー C3131
プロジェクトは、'name' プロパティに 'module' 属性を持つ必要があります。  
  
 [モジュール](../../windows/module-cpp.md)属性には、名前のパラメーターが必要です。  
  
 次の例では、C3131 が生成されます。  
  
```  
// C3131.cpp  
[emitidl];  
[module];   // C3131  
// try the following line instead  
// [module (name="MyLib")];  
  
[public]  
typedef long int LongInt;  
```
