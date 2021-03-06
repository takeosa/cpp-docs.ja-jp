---
title: "CDataConnection::operator bool (OLE DB) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataConnection::operatorBOOL"
  - "ATL::CDataConnection::operatorBOOL"
  - "CDataConnection.operatorBOOL"
  - "ATL.CDataConnection.operatorBOOL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BOOL 演算子"
  - "演算子 bool"
ms.assetid: e0791faf-2ed2-4dbb-9e68-3b9b5da2b7a7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDataConnection::operator bool (OLE DB)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在のセッションが開いているかどうかを判定します。  
  
## 構文  
  
```  
  
operator bool( ) throw( );  
  
```  
  
## 解説  
 `bool` \(C\+\+ のデータ型\) の値を返します。  **true** は 現在のセッションが開いていることを意味します。; **false** は現在のセッションが終了することを意味します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDataConnection クラス](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator BOOL](../../data/oledb/cdataconnection-operator-bool.md)