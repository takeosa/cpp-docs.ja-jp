---
title: "トランザクション オブジェクト インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interfaces, OLE DB
- transaction object interfaces
- OLE DB, interfaces
- OLE DB providers, transaction support
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5731d4d187fa02b0b68c9e4b764bf9aeb1f653dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="transaction-object-interfaces"></a>トランザクション オブジェクト インターフェイス
トランザクション オブジェクトは、データ ソース内の作業のアトミック単位を定義し、それらの作業単位が相互に関連付ける方法を決定します。 OLE DB プロバイダー テンプレートはこのオブジェクトを直接サポートされません (つまり、独自のオブジェクトを作成する必要があります)。  
  
 次の表は、トランザクション オブジェクトの OLE DB で定義されている必須およびオプションのインターフェイスを示します。  
  
|インターフェイス|必須?|OLE DB テンプレートによって実装されるか。|  
|---------------|---------------|--------------------------------------|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|必須|いいえ|  
|[ITransaction](https://msdn.microsoft.com/en-us/library/ms723053.aspx)|必須|いいえ|  
|[ISupportErrorInfo](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|Optional|いいえ|  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)