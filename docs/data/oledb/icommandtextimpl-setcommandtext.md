---
title: "ICommandTextImpl::SetCommandText | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandTextImpl.SetCommandText"
  - "ICommandTextImpl::SetCommandText"
  - "SetCommandText"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetCommandText メソッド"
ms.assetid: 7271bfb0-7a8b-4281-b3e8-7c80b9fe79d4
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ICommandTextImpl::SetCommandText
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

既存のコマンド テキストを置換コマンド テキストを設定します。  
  
## 構文  
  
```  
  
      STDMETHOD(SetCommandText)(   
   REFGUID rguidDialect,   
   LPCOLESTR pwszCommand    
);  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [ICommandTextImpl クラス](../../data/oledb/icommandtextimpl-class.md)   
 [ICommandTextImpl::GetCommandText](../../data/oledb/icommandtextimpl-getcommandtext.md)