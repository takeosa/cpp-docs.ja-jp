---
title: "C++ 整数の制限 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- limits, integer
- limits, integer constants
- integer limits
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4c1596f035da98524238e558ffe23816730aa42b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="c-integer-limits"></a>C++ 整数の制限
**Microsoft 固有の仕様**  
  
 次の表に、整数型の制限を示します。 これらの制限は、標準ヘッダー ファイル LIMITS.H で定義されます。 Microsoft C では、サイズ 8 ビット、16 ビット、または 32 ビットの整数型である、サイズ設定された整数変数も宣言できます。 サイズが設定された整数の詳細については、「[サイズ設定された整数型](../c-language/c-sized-integer-types.md)」を参照してください。  
  
### <a name="limits-on-integer-constants"></a>整数定数の制限  
  
|**定数**|説明|値|  
|------------------|-------------|-----------|  
|**CHAR_BIT**|ビット フィールドではない最小変数のビット数。|9|  
|**SCHAR_MIN**|**signed char** 型変数の最小値。|-128|  
|**SCHAR_MAX**|**signed char** 型変数の最大値。|127|  
|**UCHAR_MAX**|`unsigned char` 型変数の最大値。|255 (0xff)|  
|**CHAR_MIN**|`char` 型変数の最小値。|-128 (/J オプションが使用される場合は 0)|  
|**CHAR_MAX**|`char` 型変数の最大値。|-127 (/J オプションが使用される場合は 255)|  
|**MB_LEN_MAX**|多文字定数の最大バイト数。|5|  
|**SHRT_MIN**|**short** 型変数の最小値。|-32768|  
|**SHRT_MAX**|**short** 型変数の最大値。|32767|  
|**USHRT_MAX**|**unsigned short** 型変数の最大値。|65535 (0xffff)|  
|**INT_MIN**|`int` 型変数の最小値。|-2147483647 - 1|  
|**INT_MAX**|`int` 型変数の最大値。|2147483647|  
|**UINT_MAX**|`unsigned int` 型変数の最大値。|4294967295 (0xffffffff)|  
|**LONG_MIN**|**long** 型変数の最小値。|-2147483647 - 1|  
|**LONG_MAX**|**long** 型変数の最大値。|2147483647|  
|**ULONG_MAX**|`unsigned long` 型変数の最大値。|4294967295 (0xffffffff)|  
  
 値が最大の整数表現を超えると、Microsoft コンパイラでエラーが生成されます。  
  
 **END Microsoft 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [C 整数定数](../c-language/c-integer-constants.md)