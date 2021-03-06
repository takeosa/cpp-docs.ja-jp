---
title: "致命的なエラー C1905 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1905
dev_langs: C++
helpviewer_keywords: C1905
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9d1662b05764500d0ac6a96119f865294cac260b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1905"></a>致命的なエラー C1905
フロント エンドとバック エンドに互換性がありません (同じプロセッサを対象としなければなりません)。  
  
 このエラーが発生するのは、あるプロセッサ (x86、ARM、または [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) を対象とするコンパイラのフロントエンド (C1.dll) によって .obj ファイルが生成され、別のプロセッサを対象とするバックエンド (C2.dll) によってそのファイルが読み取られる場合です。  
  
 この問題を解決するには、一致するフロントエンドとバックエンドを使用しているか確認します。 これは、Visual Studio に作成されたプロジェクトの既定値です。 プロジェクト ファイルを編集してコンパイラ ツールへの異なるパスを使用した場合に、このエラーが表示されることがあります。 コンパイラ ツールのパスを特に設定していない場合は、Visual Studio のインストールが破損していると、このエラーが発生することがあります。 たとえば、コンパイラの .dll ファイルを 1 つの場所から別の場所にコピーした場合です。 使用して**プログラムと機能**を修復または Visual Studio を再インストールするには、Windows コントロール パネルの します。