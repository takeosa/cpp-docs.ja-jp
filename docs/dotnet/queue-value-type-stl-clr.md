---
title: "queue::value_type (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::value_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_type メンバー [STL/CLR]"
ms.assetid: f1abde03-982c-4aaf-91a6-cc613df9690e
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# queue::value_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

要素の型。  
  
## 構文  
  
```  
typedef Value value_type;  
```  
  
## 解説  
 この型は、テンプレート パラメーター `Value` のシノニムです。  
  
## 使用例  
  
```  
// cliext_queue_value_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " a b c" using value_type   
    for (; !c1.empty(); c1.pop())   
        {   // store element in value_type object   
        Myqueue::value_type val = c1.front();   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**   
## 必要条件  
 **ヘッダー:** \<cliext とキュー\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [キュー](../Topic/queue%20\(STL-CLR\).md)   
 [queue::const\_reference](../dotnet/queue-const-reference-stl-clr.md)   
 [queue::reference](../dotnet/queue-reference-stl-clr.md)