---
title: "final 指定子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: final_CPP
dev_langs: C++
helpviewer_keywords: final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1e8413e5d09cc4889445177d4b63946cda765d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="final-specifier"></a>final 指定子
`final` キーワードを使用して、派生クラスでオーバーライドできない仮想関数を指定できます。 また、このキーワードは、継承できないクラスの指定にも使用できます。  
  
## <a name="syntax"></a>構文  
  
```  
  
function-declaration final;  
```  
  
```  
  
class class-name final base-classes  
```  
  
## <a name="remarks"></a>コメント  
 `final` は状況依存のキーワードで、関数宣言またはクラス名の後で使用した場合にのみ特別な意味を持ちますが、それ以外の場合は予約済みのキーワードではありません。  
  
 `final` をクラス宣言内で使用した場合、その宣言の `base-classes` の部分は省略可能になります。  
  
## <a name="example"></a>例  
 次の例では、`final` キーワードを使用して、仮想関数をオーバーライドできないことを指定しています。  
  
```cpp  
class BaseClass  
{  
    virtual void func() final;  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void func(); // compiler error: attempting to   
                         // override a final function  
};  
```  
  
 メンバー関数をオーバーライドできることを指定する方法については、次を参照してください。[オーバーライド指定子](../cpp/override-specifier.md)です。  
  
 次の例では、`final` キーワードを使用して、クラスが継承できないことを指定しています。  
  
```cpp  
class BaseClass final   
{  
};  
  
class DerivedClass: public BaseClass // compiler error: BaseClass is   
                                     // marked as non-inheritable  
{  
};  
```  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 [override 指定子](../cpp/override-specifier.md)