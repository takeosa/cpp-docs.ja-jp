---
title: "bidirectional_iterator_tag 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xutility/std::bidirectional_iterator_tag
- bidirectional_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 33302a822cc36adf7f68d7cce29b678654aabb29
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="bidirectionaliteratortag-struct"></a>bidirectional_iterator_tag 構造体
双方向反復子を表す **iterator_category** 関数の戻り値の型を提供するクラス。  
  
## <a name="syntax"></a>構文  
  
```
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```  
  
## <a name="remarks"></a>コメント  
 カテゴリ タグ クラスがアルゴリズムの選択にコンパイル タグとして使用されます。 テンプレート関数は、コンパイル時に最も効率的なアルゴリズムを利用できるように、その反復子引数の最も具体的なカテゴリを見つける必要があります。 型 `Iterator` の反復子ごとに、反復子の動作を表す最も具体的なカテゴリ タグとして `iterator_traits`< `Iterator`>:: **iterator_category** を定義する必要があります。  
  
 この型は、**Iter** が双方向反復子としてサービスを提供するオブジェクトを表すとき、**iterator**\< **Iter**>:: **iterator_category** と同じになります。  
  
## <a name="example"></a>例  
 `bidirectional_iterator_tag` の使用方法の例については、「[random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<iterator>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [forward_iterator_tag 構造体](../standard-library/forward-iterator-tag-struct.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)




