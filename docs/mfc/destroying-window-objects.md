---
title: "ウィンドウ オブジェクトの破棄 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 67d2df7d72de079a0408847c433000a652ac6aaa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="destroying-window-objects"></a>ウィンドウ オブジェクトの破棄
注意が必要に子 windows のウィンドウで、ユーザーが終了すると、C++ ウィンドウ オブジェクトを破棄します。 これらのオブジェクトが破棄されない場合、アプリケーションはメモリを復元できません。 さいわい、フレームワークは、フレーム ウィンドウ、ビュー、およびダイアログ ボックスの作成とウィンドウの破棄を管理します。 その他のウィンドウを作成する場合を破棄します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ウィンドウの破棄順序](../mfc/window-destruction-sequence.md)  
  
-   [割り当てとウィンドウのメモリを解放します。](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Cwnd と hwnd の分離](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [一般的なウィンドウ作成順序](../mfc/general-window-creation-sequence.md)  
  
-   [フレーム ウィンドウの破棄](../mfc/destroying-frame-windows.md)  
  
## <a name="see-also"></a>関連項目  
 [Window オブジェクト](../mfc/window-objects.md)

