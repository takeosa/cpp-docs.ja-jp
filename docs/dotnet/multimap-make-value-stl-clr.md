---
title: "multimap::make_value (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multimap::make_value
dev_langs: C++
helpviewer_keywords: make_value member [STL/CLR]
ms.assetid: 9ae5ace0-e529-4247-8cd6-4e96c0611a75
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8b4c76bad9459ee26ba47602041fce6191a774ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="multimapmakevalue-stlclr"></a>multimap::make_value (STL/CLR)
値オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
static value_type make_value(key_type key, mapped_type mapped);  
```  
  
#### <a name="parameters"></a>パラメーター  
 key  
 使用するキー値。  
  
 マップ  
 検索する値をマップします。  
  
## <a name="remarks"></a>コメント  
 メンバー関数を返します、`value_type`オブジェクト キーを持つ`key`値を持つマップ`mapped`です。 他のいくつかのメンバー関数で使用するために適切なオブジェクトの作成に使用するとします。  
  
## <a name="example"></a>例  
  
```  
// cliext_multimap_make_value.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext マップ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::key_type (STL/CLR)](../dotnet/multimap-key-type-stl-clr.md)   
 [multimap::mapped_type (STL/CLR)](../dotnet/multimap-mapped-type-stl-clr.md)   
 [multimap::value_type (STL/CLR)](../dotnet/multimap-value-type-stl-clr.md)