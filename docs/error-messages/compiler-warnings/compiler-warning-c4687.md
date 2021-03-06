---
title: "コンパイラの警告 C4687 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4687
dev_langs: C++
helpviewer_keywords: C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 266213deba94bdc925747d57dee184aca5f5f605
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-c4687"></a>コンパイラの警告 C4687
'class': シールされた抽象クラスはインターフェイス 'interface' を実装できません  
  
 シールされた抽象型は通常の静的メンバー関数を保持するために便利です。  
  
 詳細については、次を参照してください。[抽象](../../windows/abstract-cpp-component-extensions.md)と[シール](../../windows/sealed-cpp-component-extensions.md)です。  
  
 既定では、エラーとして C4687 が発行されます。 C4687 を抑制することができます、[警告](../../preprocessor/warning.md)プラグマ。 シールされた抽象型にインターフェイスを実装する場合は、C4687 を抑制することができます。  
  
## <a name="example"></a>例  
 次の例では、C4687 を生成します。  
  
```  
// C4687.cpp  
// compile with: /clr /c  
interface class A {};  
  
ref struct B sealed abstract : A {};   // C4687  
ref struct C sealed : A {};   // OK  
ref struct D abstract : A {};   // OK  
```