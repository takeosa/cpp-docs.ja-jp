---
title: "&lt;list&gt; 演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- list/std::operator!=
- list/std::operator&gt;
- list/std::operator&gt;=
- list/std::operator&lt;
- list/std::operator&lt;=
- list/std::operator==
dev_langs: C++
ms.assetid: 8103d8f2-c30f-49ad-ac50-b3ba6a907ebe
caps.latest.revision: "7"
manager: ghogen
helpviewer_keywords:
- std::operator!= (list)
- std::operator&gt; (list)
- std::operator&gt;= (list)
- std::operator&lt; (list)
- std::operator&lt;= (list)
- std::operator== (list)
ms.openlocfilehash: f3834fcb728d8faf0a2148a5a0c9449fef7e41c8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ltlistgt-operators"></a>&lt;list&gt; 演算子
||||  
|-|-|-|  
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|  
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|  
  
##  <a name="op_neq"></a>  operator!=  
 演算子の左辺の list オブジェクトが右辺の list オブジェクトと等しくないかどうかを調べます。  
  
```
bool operator!=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 **list** 型のオブジェクト。  
  
 `right`  
 **list** 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 リストが等しくない場合は **true**、リストが等しい場合は **false**。  
  
### <a name="remarks"></a>コメント  
 list オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの list は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。  
  
### <a name="example"></a>例  
  
```cpp  
// list_op_ne.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
using namespace std;  
list <int> c1, c2;  
c1.push_back( 1 );  
c2.push_back( 2 );  
  
if ( c1 != c2 )  
cout << "Lists not equal." << endl;  
else  
cout << "Lists equal." << endl;  
}  
\* Output:  
Lists not equal.  
*\  
```  
  
##  <a name="op_lt"></a>  operator&lt;  
 演算子の左辺の list オブジェクトが右辺の list オブジェクトより小さいかどうかを調べます。  
  
```
bool operator<(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 **list** 型のオブジェクト。  
  
 `right`  
 **list** 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の list が演算子の右辺の list 未満である場合は **true**、それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 list オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つのオブジェクト間の小なり関係は、最初の等しくない要素のペアの比較に基づいています。  
  
### <a name="example"></a>例  
  
```cpp  
// list_op_lt.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 4 );  
  
   c2.push_back( 1 );  
   c2.push_back( 3 );  
  
   if ( c1 < c2 )  
      cout << "List c1 is less than list c2." << endl;  
   else  
      cout << "List c1 is not less than list c2." << endl;  
}  
\* Output:   
List c1 is less than list c2.  
*\   
```  
  
##  <a name="op_lt_eq"></a>  operator&lt;=  
 演算子の左辺の list オブジェクトが右辺の list オブジェクト以下かどうかを調べます。  
  
```
bool operator<=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 **list** 型のオブジェクト。  
  
 `right`  
 **list** 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の list が演算子の右辺の list 以下である場合は **true**、それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 list オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つのオブジェクト間の "以下" 関係は、最初の等しくない要素のペアの比較に基づいています。  
  
### <a name="example"></a>例  
  
```cpp  
// list_op_le.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 4 );  
  
   c2.push_back( 1 );  
   c2.push_back( 3 );  
  
   if ( c1 <= c2 )  
      cout << "List c1 is less than or equal to list c2." << endl;  
   else  
      cout << "List c1 is greater than list c2." << endl;  
}  
\* Output:   
List c1 is less than or equal to list c2.  
*\  
```  
  
##  <a name="op_eq_eq"></a>  operator==  
 演算子の左辺の list オブジェクトが右辺の list オブジェクトと等しいかどうかを調べます。  
  
```
bool operator==(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 **list** 型のオブジェクト。  
  
 `right`  
 **list** 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の list が演算子の右辺の list と等しい場合は **true**、それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 list オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの list は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。  
  
### <a name="example"></a>例  
  
```cpp  
// list_op_eq.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
int main( )   
{  
   using namespace std;   
  
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c2.push_back( 1 );  
  
   if ( c1 == c2 )  
      cout << "The lists are equal." << endl;  
   else  
      cout << "The lists are not equal." << endl;  
}  
\* Output:   
The lists are equal.  
*\  
```  
  
##  <a name="op_gt"></a>  operator&gt;  
 演算子の左辺の list オブジェクトが右辺の list オブジェクトより大きいかどうかを調べます。  
  
```
bool operator>(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 **list** 型のオブジェクト。  
  
 `right`  
 **list** 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の list が演算子の右辺の list より大きい場合は **true**、それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 list オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つのオブジェクト間の大なり関係は、最初の等しくない要素のペアの比較に基づいています。  
  
### <a name="example"></a>例  
  
```cpp  
// list_op_gt.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
int main( )   
{  
   using namespace std;   
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c1.push_back( 3 );  
   c1.push_back( 1 );  
  
   c2.push_back( 1 );  
   c2.push_back( 2 );  
   c2.push_back( 2 );  
  
   if ( c1 > c2 )  
      cout << "List c1 is greater than list c2." << endl;  
   else  
      cout << "List c1 is not greater than list c2." << endl;  
}  
\* Output:   
List c1 is greater than list c2.  
*\  
```  
  
##  <a name="op_gt_eq"></a>  operator&gt;=  
 演算子の左辺の list オブジェクトが右辺の list オブジェクト以上かどうかを調べます。  
  
```
bool operator>=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 **list** 型のオブジェクト。  
  
 `right`  
 **list** 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の list が演算子の右辺の list 以上である場合は **true**、それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 list オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つのオブジェクト間の "以上" 関係は、最初の等しくない要素のペアの比較に基づいています。  
  
### <a name="example"></a>例  
  
```cpp  
// list_op_ge.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
   list <int> c1, c2;  
   c1.push_back( 1 );  
   c1.push_back( 3 );  
   c1.push_back( 1 );  
  
   c2.push_back( 1 );  
   c2.push_back( 2 );  
   c2.push_back( 2 );  
  
   if ( c1 >= c2 )  
      cout << "List c1 is greater than or equal to list c2." << endl;  
   else  
      cout << "List c1 is less than list c2." << endl;  
}  
\* Output:   
List c1 is greater than or equal to list c2.  
*\  
```  
  
## <a name="see-also"></a>関連項目  
 [\<list>](../standard-library/list.md)



