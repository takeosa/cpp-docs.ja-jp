---
title: "_mm_cvtsi64x_ss |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mm_cvtsi64x_ss
dev_langs: C++
helpviewer_keywords:
- cvtsi2ss instruction
- _mm_cvtsi64x_ss intrinsic
ms.assetid: 01e5d321-c18a-46fd-a6f6-324364514e1f
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aecb28648e32e099d2381fa49b1b7f5a42618543
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="mmcvtsi64xss"></a>_mm_cvtsi64x_ss
**Microsoft 固有の仕様**  
  
 生成、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]スカラー単精度浮動小数点値に変換する 64 ビット整数の拡張のバージョン (`cvtsi2ss`) 命令します。  
  
## <a name="syntax"></a>構文  
  
```  
__m128 _mm_cvtsi64x_ss(   
   __m128 a,   
   __int64 b   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `a`  
 `__m128` 4 つの単精度浮動小数点値を含む構造体。  
  
 [入力] `b`  
 浮動小数点値に変換する 64 ビット整数。  
  
## <a name="return-value"></a>戻り値  
 `__m128`構造体の最初の浮動小数点値は変換の結果。 その他の 3 つの値から変更されていないコピー`a`です。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_mm_cvtsi64x_ss`|x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 `__m128`構造は XMM レジスタを表し、そのため、この組み込みの値を許可する`b`XMM に移動されるシステム メモリから登録します。  
  
 このルーチンは、組み込みとしてのみ使用できます。  
  
## <a name="example"></a>例  
  
```  
// _mm_cvtsi64x_ss.cpp  
// processor: x64  
  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtsi64x_ss)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    a.m128_f32[0] = 0;  
    a.m128_f32[1] = 0;  
    a.m128_f32[2] = 0;  
    a.m128_f32[3] = 0;  
    a = _mm_cvtsi64x_ss(a, b);  
  
    printf_s( "%lf %lf %lf %lf\n",  
              a.m128_f32[0], a.m128_f32[1],   
              a.m128_f32[2], a.m128_f32[3] );  
}  
```  
  
```Output  
54.000000 0.000000 0.000000 0.000000  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_ _m128](../cpp/m128.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)