---
title: "Platform::collections: クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLLECTION/Platform::Collections::Map::Map
- COLLECTION/Platform::Collections::Map::Clear
- COLLECTION/Platform::Collections::Map::First
- COLLECTION/Platform::Collections::Map::GetView
- COLLECTION/Platform::Collections::Map::HasKey
- COLLECTION/Platform::Collections::Map::Insert
- COLLECTION/Platform::Collections::Map::Lookup
- COLLECTION/Platform::Collections::Map::Remove
- COLLECTION/Platform::Collections::Map::Size
dev_langs: C++
helpviewer_keywords: Map Class (C++/Cx)
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
caps.latest.revision: "19"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 3cf7cec405170a1bb1ee02cfd076c78c43524c74
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="platformcollectionsmap-class"></a>Platform::Collections::Map クラス
キー/値ペアのコレクションである *マップ*を表します。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = std::less<K>>  
ref class Map sealed;  
```  
#### <a name="parameters"></a>パラメーター  
 `K`  
 キー/値ペア内のキーの型。  
  
 `V`  
 キー/値ペア内の値の型。  
  
 `C`  
 並べ替えキーとして 2 つの要素値を比較してマップ内の相対順序を決定できる関数オブジェクトを提供する型。 既定では、 [std::less\<K >](../standard-library/less-struct.md)です。  
  
 __is_valid_winrt_type()  
 K および V の型を検証し、型がマップ内に格納できない場合は簡易エラー メッセージを示す、コンパイラにより生成される関数。  
  
### <a name="remarks"></a>コメント  
 使用できる型は次のとおりです。  
  
-   整数  
  
-   インターフェイス クラス ^  
  
-   パブリック ref クラス ^  
  
-   value struct  
  
-   パブリック列挙型クラス  
  
 マップは、基本的に [std::map](../standard-library/map-class.md)のラッパーです。 C++ の具象実装は、 [Windows::Foundation::Collections::IMap < Windows::Foundation::Collections::IKeyValuePair\<K, V >>](http://go.microsoft.com/fwlink/p/?LinkId=262408)と[IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx)Windows ランタイム インターフェイスのパブリックの間で渡される型。 パブリックの戻り値またはパラメーターで `Platform::Collections::Map` 型を使用しようとすると、コンパイラ エラー C3986 が発生します。 パラメーターまたは戻り値の型を変更することで、エラーを修正することができます[Windows::Foundation::Collections::IMap\<K, V >](http://go.microsoft.com/fwlink/p/?LinkId=262408)です。  
  
 詳細については、次を参照してください。[コレクション](../cppcx/collections-c-cx.md)です。  
  
### <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Map::map](#ctor)|マップ クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Map::clear](#clear)|現在のマップ オブジェクトから、すべてのキー/値ペアを削除します。|  
|[Map::first](#first)|マップ内の最初の要素を指定する反復子を返します。|  
|[Map::getview](#getview)|現在のマップの読み取り専用ビュー ( [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md)) を返します。|  
|[Map::haskey](#haskey)|指定したキーが現在のマップに格納されているかどうかを判定します。|  
|[Map::insert](#insert)|指定したキー/値ペアを現在のマップ オブジェクトに追加します。|  
|[Map::lookup](#lookup)|現在のマップ オブジェクト内の指定されたキーの位置の要素を取得します。|  
|[Map::remove](#remove)|指定したキー/値ペアを現在のマップ オブジェクトから削除します。|  
|[Map::size](#size)|現在のマップ オブジェクト内の要素数を返します。|  
  
### <a name="events"></a>イベント  
  
|||  
|-|-|  
|名前|説明|  
|[Map::mapchanged](#mapchanged-event.md)`event`|マップが変更されたときに発生します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Map`  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  

## <a name="clear"></a>Map::clear メソッド
現在のマップ オブジェクトから、すべてのキー/値ペアを削除します。  
  
### <a name="syntax"></a>構文  
  
```    
virtual void Clear();   
```  
  


## <a name="first"></a>Map::first メソッド
マップ内の最初の要素を指定する反復子、またはマップが空の場合は `nullptr` を返します。  
  
### <a name="syntax"></a>構文  
  
```    
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
### <a name="return-value"></a>戻り値  
 マップ内の最初の要素を指定する反復子。  
  
### <a name="remarks"></a>コメント  
 First() によって返される反復子を保持する便利な方法で宣言された変数に戻り値を割り当てるには、**自動**推論キーワードを入力します。 たとえば、`auto x = myMap->First();` のようにします。  
  


## <a name="getview"></a>Map::getview メソッド
現在のマップの読み取り専用ビューを返しますつまり、 [Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)を実装する、 [Windows::Foundation::Collections::IMapView\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226037.aspx)インターフェイスです。  
  
### <a name="syntax"></a>構文  
  
```    
Windows::Foundation::Collections::IMapView<K, V>^ GetView();  
```  
  
### <a name="return-value"></a>戻り値  
 `MapView` オブジェクト。  
  


## <a name="haskey"></a>Map::haskey メソッド
指定したキーが現在のマップに格納されているかどうかを判定します。  
  
### <a name="syntax"></a>構文  
  
```    
bool HasKey(K key);  
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 Map 要素の検索に使用するキー。 型`key`typename は*K*です。  
  
### <a name="return-value"></a>戻り値  
 キーが見つかった場合は `true`。それ以外の場合は `false`。  
  


## <a name="insert"></a>Map::insert メソッド
指定したキー/値ペアを現在のマップ オブジェクトに追加します。  
  
### <a name="syntax"></a>構文  
  
```  
  
virtual bool Insert(K key, V value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 キー/値ペアのキー部分。 型`key`typename は*K*です。  
  
 `value`  
 キー/値ペアの値部分。 型`value`typename は*V*です。  
  
### <a name="return-value"></a>戻り値  
 現在のマップ内の既存要素のキーが `true` と一致し、その要素の値部分が `key` に設定されている場合は `value`。 現在のマップ内の既存要素が `false` と一致せず、`key` および `key` パラメーターがキー/値ペアになっていて、現在のマップに追加されている場合は `value`。  
  


## <a name="lookup"></a>Map::lookup メソッド
キーがある場合は、型 K の指定されたキーに関連付けられている型 V の値を取得します。  
  
### <a name="syntax"></a>構文  
  
```  
V Lookup(K key);  
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 マップの要素の検索に使用するキー。 型`key`typename は*K*です。  
  
### <a name="return-value"></a>戻り値  
 `key` とペアになる値。 戻り値の型は typename *V*です。  
  
### <a name="remarks"></a>コメント  
 キーが存在しない場合、 [platform::outofboundsexception](../cppcx/platform-outofboundsexception-class.md)がスローされます。  
  


## <a name="ctor"></a>Map::map コンス トラクター
マップ クラスの新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```  
explicit Map(const C& comp = C());  
explicit Map(const StdMap& m);  
explicit Map(StdMap&& m ;  
template <typename InIt>  
Map(  
   InItfirst,  
   InItlast,  
   const C& comp = C());  
```  
  
### <a name="parameters"></a>パラメーター  
 `InIt`  
 現在のマップの型名。  
  
 `comp`  
 並べ替えキーとして 2 つの要素値を比較してマップ内の相対順序を決定できる関数オブジェクトを提供する型。  
  
 `m`  
 参照または[Lvalue と Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)を`map Class`現在のマップを初期化するために使用されます。  
  
 `first`  
 現在のマップを初期化するために使用される要素の範囲内の最初の要素の入力反復子。  
  
 `last`  
 現在のマップを初期化するために使用される要素の範囲の後の最初の要素の入力反復子。  
  


## <a name="mapchanged"></a>Map::mapchanged イベント
項目がマップに挿入されたときまたはマップから削除されたときに発生します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;  
```  
  
### <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 A [MapChangedEventHandler\<K, V >](http://msdn.microsoft.com/library/windows/apps/br206644.aspx)イベント、および発生した変更の種類を発生させたオブジェクトに関する情報を格納します。 関連項目[IMapChangedEventArgs\<K >](http://msdn.microsoft.com/library/windows/apps/br226034.aspx)と[collectionchange Enumeration 列挙型](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx)です。  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 C# または Visual Basic を使用する Windows ストア アプリ プロジェクト IMap\<K, V > を IDictionary として\<K, V >。  
  


## <a name="remove"></a>Map::remove メソッド
指定したキー/値ペアを現在のマップ オブジェクトから削除します。  
  
### <a name="syntax"></a>構文  
  
```    
virtual void Remove(K key);  
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 キー/値ペアのキー部分。 型`key`typename は*K*です。  
  


## <a name="size"></a>Map::size メソッド
数を返します[Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx)マップ内の要素。  
  
### <a name="syntax"></a>構文  
  
```    
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>戻り値  
 マップの要素数。  
  

  
## <a name="see-also"></a>関連項目  
 [プラットフォーム Namespace](platform-namespace-c-cx.md)   
 [C++ での Windows ランタイム コンポーネントを作成します。](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md)