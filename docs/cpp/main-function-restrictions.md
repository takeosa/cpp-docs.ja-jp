---
title: "main 関数に関する制約 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Main
dev_langs:
- C++
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 10fe82b0bb7ad700164b05ba466854db7716ba76
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="main-function-restrictions"></a>main 関数に関する制約
いくつかの制限を適用する、**メイン**関数を他の C++ 関数には適用されません。 **メイン**関数。  
  
-   オーバー ロードできません (を参照してください[関数のオーバー ロード](function-overloading.md))。  
  
-   として宣言することはできません**インライン**です。  
  
-   として宣言することはできません**静的**です。  
  
-   そのアドレスを取得することはできません。  
  
-   呼び出すことはできません。  
  
## <a name="see-also"></a>関連項目  
 [main: プログラムの起動](../cpp/main-program-startup.md)
