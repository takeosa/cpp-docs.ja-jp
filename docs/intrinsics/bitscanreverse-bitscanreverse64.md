---
title: "_BitScanReverse、_BitScanReverse64 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _BitScanReverse64
- _BitScanReverse_cpp
- _BitScanReverse
- _BitScanReverse64_cpp
dev_langs: C++
helpviewer_keywords:
- bsr instruction
- _BitScanReverse intrinsic
- BitScanReverse intrinsic
ms.assetid: 2520a207-af8b-4aad-9ae7-831abeadf376
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1547a5aa4ab4709c47305bd5097ba138171fd71c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="bitscanreverse-bitscanreverse64"></a>_BitScanReverse、_BitScanReverse64
**Microsoft 固有の仕様**  
  
 マスク データの最上位ビット (MSB) から最下位ビット (LSB) に向かって設定済みビット (1) を検索します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char _BitScanReverse(  
   unsigned long * Index,  
   unsigned long Mask  
);  
unsigned char _BitScanReverse64(  
   unsigned long * Index,  
   unsigned __int64 Mask  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `Index`  
 最初に見つかった設定済みビット (1) のビット位置が読み込まれます。  
  
 [入力] `Mask`  
 検索する 32 ビットまたは 64 ビットの値。  
  
## <a name="return-value"></a>戻り値  
 `Index` が設定された場合は 0 以外、設定済みビットが見つからなかった場合は 0。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|Header|  
|---------------|------------------|------------|  
|`_BitScanReverse`|x86、ARM、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h >|  
|`_BitScanReverse64`|ARM、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]||  
  
## <a name="example"></a>例  
  
```  
// BitScanReverse.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(_BitScanReverse)  
  
int main()  
{  
   unsigned long mask = 0x1000;  
   unsigned long index;  
   unsigned char isNonzero;  
  
   cout << "Enter a positive integer as the mask: " << flush;  
   cin >> mask;  
   isNonzero = _BitScanReverse(&index, mask);  
   if (isNonzero)  
   {  
      cout << "Mask: " << mask << " Index: " << index << endl;  
   }  
   else  
   {  
      cout << "No set bits found.  Mask is zero." << endl;  
   }  
}  
```  
  
## <a name="input"></a>入力  
  
```  
12  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
Enter a positive integer as the mask:   
Mask: 12 Index: 3  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)