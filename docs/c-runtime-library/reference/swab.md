---
title: _swab | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _swab
- stdlib/_swab
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _swab
- stdlib/_swab
dev_langs: C++
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a3043abf425055d8cb21108a30db2e6382e19c1a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="swab"></a>_swab
バイトを交換します。  
  
## <a name="syntax"></a>構文  
  
```  
void _swab(  
   char *src,  
   char *dest,  
   int n   
);  
```  
  
## <a name="parameters"></a>パラメーター  
 `src`  
 コピーおよび交換されるデータ。  
  
 `dest`  
 交換したデータの格納場所。  
  
 `n`  
 コピーおよび交換対象のバイト数。  
  
## <a name="return-value"></a>戻り値
 `swab` 関数は値を返しません。 `src` または `dest` のポインターが NULL である場合、または `n` がゼロ未満の場合、この関数は `errno` を `EINVAL` に設定し、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。  
  
 戻り値の詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。
 
## <a name="remarks"></a>コメント  
 `n` が偶数の場合、`_swab` 関数は `src` から `n` バイトをコピーし、隣接するバイトの各ペアをスワップして、結果を `dest` に格納します。 `n` が奇数の場合、`_swab` 関数は `src` の最初の `n-1` バイトをコピーしてスワップします。最後のバイトはコピーされません。 `_swab` 関数は、通常、異なるバイト順を使用するコンピューターに転送するバイナリ データを準備するときに使用されます。  
  
## <a name="requirements"></a>要件  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_swab`|C: \<stdlib.h> C++: \<cstdlib> または \<stdlib.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
```C 
// crt_swab.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";  
char to[] =   "...........................";  
  
int main()  
{  
    printf("Before: %s  %d bytes\n        %s\n\n", from, sizeof(from), to);  
    _swab(from, to, sizeof(from));  
    printf("After:  %s\n        %s\n\n", from, to);  
}  
```  
  
```Output  
Before: BADCFEHGJILKNMPORQTSVUXWZY  27 bytes  
        ...........................  
  
After:  BADCFEHGJILKNMPORQTSVUXWZY  
        ABCDEFGHIJKLMNOPQRSTUVWXYZ.  
```  
  
## <a name="see-also"></a>関連項目  
 [バッファー操作](../../c-runtime-library/buffer-manipulation.md)