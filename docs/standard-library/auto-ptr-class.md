---
title: "auto_ptr クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::auto_ptr
- memory/std::auto_ptr::element_type
- memory/std::auto_ptr::get
- memory/std::auto_ptr::release
- memory/std::auto_ptr::reset
dev_langs: C++
helpviewer_keywords:
- std::auto_ptr [C++]
- std::auto_ptr [C++], element_type
- std::auto_ptr [C++], get
- std::auto_ptr [C++], release
- std::auto_ptr [C++], reset
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c7411a11a396627fb01d1dad1d47dc957ce968a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="autoptr-class"></a>auto_ptr クラス
コントロールがあるブロックを離れるときに確実にリソースが自動的に破棄されるように、リソースの周囲にスマート ポインターをラップします。  
  
 より高機能なこの `unique_ptr` クラスは `auto_ptr` に代わるものです。 詳細については、「[unique_ptr クラス](../standard-library/unique-ptr-class.md)」をご覧ください。  
  
 `throw()` および例外処理の詳細については、「[例外の仕様 (スロー)](../cpp/exception-specifications-throw-cpp.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
 ```   
class auto_ptr {
public:
    typedef Type element_type;
    explicit auto_ptr(Type* ptr = 0) throw();
    auto_ptr(auto_ptr<Type>& right) throw()
        ;
    template <class Other>
    operator auto_ptr<Other>() throw();
    template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
    template <class Other>
    auto_ptr(auto_ptr<Other>& right);
    auto_ptr<Type>& operator=(auto_ptr<Type>& right);
    ~auto_ptr();
    Type& operator*() const throw();
    Type * operator->()const throw();
    Type *get() const throw();
    Type *release()throw();
    void reset(Type* ptr = 0);
};
```  
#### <a name="parameters"></a>パラメーター  
 `right`  
 既存のリソースの取得元となる `auto_ptr`。  
  
 `ptr`  
 格納されたポインターを置換するように指定されたポインター。  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスと呼ばれる、スマート ポインターを記述する、 `auto_ptr`、割り当てられたオブジェクトにします。 このポインターは、null であるか、`new` によって割り当てられたオブジェクトを指定する必要があります。 `auto_ptr` は、格納されている値が別のオブジェクトに割り当てられている場合、所有権を転送します。 (転送後、格納されている値は null ポインターに置換されます。)`auto_ptr<Type>` のデストラクターが割り当てられたオブジェクトを削除します。 `auto_ptr<Type>` は、コントロールがブロックを離れるとき、例外がスローされる場合であっても、割り当てられたオブジェクトが確実に自動的に削除するようにします。 同じオブジェクトを所有する 2 つの `auto_ptr<Type>` オブジェクトを構成しないでください。  
  
 `auto_ptr<Type>` オブジェクトを関数呼び出しの引数として値渡しで渡せます。 `auto_ptr` を標準ライブラリのコンテナーの要素にすることはできません。 C++ 標準ライブラリのコンテナーを持つ `auto_ptr<Type>` オブジェクトのシーケンスを確実に管理することはできません。  
  
## <a name="members"></a>メンバー  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[auto_ptr](#auto_ptr)|`auto_ptr` 型のオブジェクトのコンストラクター。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[element_type](#element_type)|この型は、テンプレート パラメーター `Type` のシノニムです。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[get](#get)|このメンバー関数は、格納されているポインター `myptr` を返します。|  
|[release](#release)|このメンバーは、格納されたポインター `myptr` を null ポインターで置換して、以前に格納されたポインターを返します。|  
|[reset](#reset)|このメンバー関数は、関数呼び出しの結果として格納されているポインター値 `myptr` が変化する場合に限り、式 `delete myptr` を評価します。 その後、格納されたポインターを `ptr` で置換します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator=](#op_eq)|1 つの `auto_ptr` オブジェクトから別のオブジェクトに所有権を転送する代入演算子。|  
|[operator*](#op_star)|`auto_ptr` 型のオブジェクトの逆参照演算子。|  
|[operator->](#operator-_gt)|メンバーにアクセスできるようにする演算子。|  
|[operator auto_ptr\<Other>](#op_auto_ptr_lt_other_gt)|1 つの種類の `auto_ptr` から別の種類の `auto_ptr` にキャストします。|  
|[operator auto_ptr_ref\<Other>](#op_auto_ptr_ref_lt_other_gt)|`auto_ptr` から `auto_ptr_ref` にキャストします。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<memory>  
  
 **名前空間:** std  
  
##  <a name="auto_ptr"></a>  auto_ptr::auto_ptr  
 `auto_ptr` 型のオブジェクトのコンストラクター。  
  
```   
explicit auto_ptr(Type* ptr  = 0) throw();

auto_ptr(auto_ptr<Type>& right) throw();

auto_ptr(auto _ptr_ref<Type> right) throw();

template <class Other>  
auto _ptr(auto _ptr<Other>& right) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ptr`  
 `auto_ptr` がカプセル化するオブジェクトへのポインター。  
  
 `right`  
 コンストラクターによってコピーされる `auto_ptr` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターは、`ptr` を **myptr** (割り当てられたオブジェクトへの格納されたポインター) に格納します。 2 番目のコンストラクターは、`right` に格納されているポインターの所有権を転送します。これは `right`. [release](#release) を **myptr** に格納することで行います。  
  
 3 番目のコンストラクターは 2 番目と同じ動作をしますが、**right**. `ref`。 **release** を **myptr** に格納する点が異なります。ここで、`ref` は `right` に格納されている参照です。  
  
 テンプレート コンストラクターの動作は、**Other** へのポインターが **Type** に暗黙的に変換できる場合は、2 番目のコンストラクターと同じです。  
  
### <a name="example"></a>例  
  
```cpp  
// auto_ptr_auto_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Int   
{  
public:  
   Int(int i)   
   {  
      cout << "Constructing " << ( void* )this  << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
   ~Int( )   
   {  
      cout << "Destructing " << ( void* )this << endl;   
      bIsConstructed = false;  
   };  
   Int &operator++( )   
   {  
      x++;  
      return *this;  
   };  
   int x;  
private:  
   bool bIsConstructed;  
};  
  
void function ( auto_ptr<Int> &pi )  
{  
   ++( *pi );  
   auto_ptr<Int> pi2( pi );  
   ++( *pi2 );  
   pi = pi2;  
}  
  
int main( )   
{  
   auto_ptr<Int> pi ( new Int( 5 ) );  
   cout << pi->x << endl;  
   function( pi );  
   cout << pi->x << endl;  
}  
```  
  
```Output  
Constructing 00311AF8  
5  
7  
Destructing 00311AF8  
```  
  
##  <a name="element_type"></a>  auto_ptr::element_type  
 この型は、テンプレート パラメーター **Type** のシノニムです。  
  
```  
 
typedef Type element  _type;  
```  
  
##  <a name="get"></a>  auto_ptr::get  
 このメンバー関数は、格納されているポインター **myptr** を返します。  
  
```   
Type *get() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 格納されているポインター **myptr**。  
  
### <a name="example"></a>例  
  
```cpp  
// auto_ptr_get.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class Int   
{  
public:  
   Int(int i)   
   {  
      x = i;  
      cout << "Constructing " << ( void* )this  << " Value: " << x << endl;   
   };  
   ~Int( )   
   {  
      cout << "Destructing " << ( void* )this << " Value: " << x << endl;   
   };  
  
   int x;  
  
};  
  
int main( )   
{  
   auto_ptr<Int> pi ( new Int( 5 ) );  
   pi.reset( new Int( 6 ) );  
   Int* pi2 = pi.get ( );  
   Int* pi3 = pi.release ( );  
   if (pi2 == pi3)  
      cout << "pi2 == pi3" << endl;  
   delete pi3;  
}  
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
##  <a name="op_eq"></a>  auto_ptr::operator=  
 1 つの `auto_ptr` オブジェクトから別のオブジェクトに所有権を転送する代入演算子。  
  
```  
template <class Other>  
auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
auto_ptr<Type>& operator=(auto_ptr<Type>& right) throw();
auto_ptr<Type>& operator=(auto_ptr_ref<Type> right) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 `auto_ptr` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 型 `auto_ptr`\< **Type**> のオブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 この割り当ては、割り当ての結果として格納されているポインター値 **myptr** が変化する場合に限り、式 **delete myptr** を評価します。 その後、*Right* に格納されているポインターの所有権を転送します。これは、\_ *Right*. [release](#release) を **myptr** に格納することで行います。 関数は **\*this** を返します。  
  
### <a name="example"></a>例  
  メンバー演算子の使用例は、「[auto_ptr::auto_ptr](#auto_ptr)」を参照してください。  
  
##  <a name="op_star"></a>  auto_ptr::operator*  
 `auto_ptr` 型のオブジェクトの逆参照演算子。  
  
```   
Type& operator*() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターが所有する型 **Type** のオブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 間接演算子は `*`[get](#get) を返します。 つまり、格納されたポインターは、null にすることはできません。  
  
### <a name="example"></a>例  
  メンバー関数の使用方法の例は、「[auto_ptr::auto_ptr](#auto_ptr)」を参照してください。  
  
##  <a name="auto_ptr__operator-_gt"></a>  auto_ptr::operator-&gt;  
 メンバーにアクセスできるようにする演算子。  
  
```   
Type * operator->() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 **auto_ptr** が所有するオブジェクトのメンバー。  
  
### <a name="remarks"></a>コメント  
 選択演算子は [get](#get)`( )` を返して、式 *ap*-> **member** が ( *ap*. **get**( ) )-> **member** と同じ動作をするようにします。ここで、*ap* はクラス `auto_ptr`\< **Type**> のオブジェクトです。 そのため、格納されているポインターを null にすることはできず、**Type** はメンバー **member** を持つクラス、構造体、または共用体型にする必要があります。  
  
### <a name="example"></a>例  
  メンバー関数の使用方法の例は、「[auto_ptr::auto_ptr](#auto_ptr)」を参照してください。  
  
##  <a name="op_auto_ptr_lt_other_gt"></a>  auto_ptr::operator auto_ptr&lt;Other&gt;  
 1 つの種類の `auto_ptr` から別の種類の `auto_ptr` にキャストします。  
  
```   
template <class Other>  
operator auto _ptr<Other>() throw();
```  
  
### <a name="return-value"></a>戻り値  
 型キャスト演算子は `auto_ptr` \< **Other**>( **\*this**) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// auto_ptr_op_auto_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
int main()  
{  
   auto_ptr<int> pi ( new int( 5 ) );  
   auto_ptr<const int> pc = ( auto_ptr<const int> )pi;  
}  
```  
  
##  <a name="op_auto_ptr_ref_lt_other_gt"></a>  auto_ptr::operator auto_ptr_ref&lt;Other&gt;  
 `auto_ptr` から **auto_ptr_ref** にキャストします。  
  
```   
template <class Other>  
operator auto _ptr  _ref<Other>() throw();
```  
  
### <a name="return-value"></a>戻り値  
 型キャスト演算子は **auto_ptr_ref**\< **Other**>( **\*this**) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// auto_ptr_op_auto_ptr_ref.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class C {
public:
    C(int _i) : m_i(_i) {
    }
    ~C() {
        cout << "~C:  " << m_i << "\n";
    }
    C &operator =(const int &x) {
        m_i = x;
        return *this;
    }
    int m_i;
};
void f(auto_ptr<C> arg) {
};
int main()
{
    const auto_ptr<C> ciap(new C(1));
    auto_ptr<C> iap(new C(2));

    // Error: this implies transfer of ownership of iap's pointer  
    // f(ciap);   
    f(iap); // compiles, but gives up ownership of pointer  

            // here, iap owns a destroyed pointer so the following is bad:  
            // *iap = 5; // BOOM  

    cout << "main exiting\n";
}
```  
  
```Output  
~C:  2  
main exiting  
~C:  1  
```  
  
##  <a name="release"></a>  auto_ptr::release  
 このメンバーは、格納されたポインター **myptr** を null ポインターで置換して、以前に格納されたポインターを返します。  
  
```   
Type *release() throw();
```  
  
### <a name="return-value"></a>戻り値  
 以前に格納されたポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバーは、格納されたポインター **myptr** を null ポインターで置換して、以前に格納されたポインターを返します。  
  
### <a name="example"></a>例  
  
```cpp  
// auto_ptr_release.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int() {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;

};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
##  <a name="reset"></a>  auto_ptr::reset  
 このメンバー関数は、式を評価する**削除** **myptr**、場合に限り、格納されているポインター値**myptr**関数呼び出しの結果として変更します。 その後、格納されたポインターを **ptr** で置換します。  
  
```   
void reset(Type* ptr = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptr`  
 格納されたポインター **myptr** を置換するように指定されたポインター。  
  
### <a name="example"></a>例  
  
```cpp  
// auto_ptr_reset.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;

class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int()
    {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;
};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [unique_ptr クラス](../standard-library/unique-ptr-class.md)

