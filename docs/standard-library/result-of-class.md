---
title: "result_of クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
dev_langs:
- C++
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 08e4fc22725962d06bee35ed1adf63e3c9230ced
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="resultof-class"></a>result_of クラス
指定された引数型を受け取る呼び出し可能型の戻り値の型を決定します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class>  
struct result_of; // Causes a static assert  
  
template <class Fn, class... ArgTypes>  
struct result_of<Fn(ArgTypes...)>;

// Helper type  
template<class T>
   using result_of_t = typename result_of<T>::type;
```  
  
#### <a name="parameters"></a>パラメーター  
 `Fn`  
 照会する呼び出し可能型。  
  
 `ArgTypes`  
 照会する呼び出し可能型の引数リストの種類。  
  
## <a name="remarks"></a>コメント  
 このテンプレートを使用して、コンパイル時に、結果の型 `Fn`(`ArgTypes`) を指定します。ここで、`Fn` は呼び出し可能型、関数への参照、または `ArgTypes` の型の引数リストを使用して呼び出される呼び出し可能型への参照です。 評価されていない式 `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` が整形式の場合、テンプレート クラスの `type` メンバーによって、`decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))` の結果の型が指定されます。 それ以外の場合、このテンプレート クラスはメンバー `type` を持ちません。 `Fn` 型とパラメーター パック `ArgTypes` のすべての型は、完全な型、`void`、または不明なバインドの配列にする必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)




