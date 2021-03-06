---
title: "デバイス イメージ (アイコン用イメージ エディター) を作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.icon
dev_langs: C++
helpviewer_keywords:
- cursors [C++], creating
- icons [C++], creating
- display devices
- display devices, creating image
- images [C++], creating for display devices
- icons [C++], inserting
ms.assetid: 5a536928-32df-4ace-beb1-1521ce3b871f
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8a4f71b2877eaaa7af125918c7fe2b71bb031d39
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-device-image-image-editor-for-icons"></a>デバイス イメージの作成 (アイコン用イメージ エディター)
特定のスタイル (32 × 32 の 16 色のアイコンと 32 × 32 のカーソルのモノクロ) でイメージをまず作成とリソースを作成する新しいアイコンまたはカーソル、イメージ エディターします。 初期のアイコンまたはカーソルをさまざまなサイズとスタイルのイメージを追加し、別のディスプレイ デバイスの場合、必要に応じて、追加したイメージを編集できます。 既存のイメージの種類とは、グラフィック プログラムで作成されたビットマップからカット アンド ペースト操作を実行してイメージを編集することもできます。  
  
 アイコンまたはカーソルのリソースを開くと、[イメージ エディター](../windows/image-editor-for-icons.md)既定ではほとんど密接に一致する現在のディスプレイ デバイスが開かれたイメージ。  
  
### <a name="to-create-a-new-icon-or-cursor"></a>新しいアイコンやカーソルを作成するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)、.rc ファイルを右クリックし **リソースの挿入**ショートカット メニューからです。 (を単に右クリック、カーソルなど、.rc ファイルに既存のイメージ リソースがある場合、**カーソル**フォルダーを選択**挿入カーソル**ショートカット メニューからです)。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  [リソースの挿入 ダイアログ ボックス](../windows/add-resource-dialog-box.md)[**アイコン**または**カーソル**] をクリック**新規**です。 アイコンは、32 × 32 の 16 色のアイコンを使用この、アイコン リソースを作成します。 カーソルについては、32 × 32 のモノクロ (2 色) イメージが作成されます。  
  
     場合は、プラス記号 (**+**) で画像リソースの種類の横に表示される、**リソースの挿入**ツールバーのテンプレートが使用できることを意味、ダイアログ ボックスで、します。 テンプレートの一覧を展開し、テンプレートを選択してをクリックするには、プラス記号をクリックして**新規**です。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](https://msdn.microsoft.com/library/f45fce5x.aspx)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](https://msdn.microsoft.com/library/xbx3z216.aspx)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](https://msdn.microsoft.com/library/h6270d0z.aspx)です。  
  
 **Requirements**  
  
 なし  
  
## <a name="see-also"></a>関連項目  
 [アイコンとカーソル: ディスプレイ デバイスのイメージ リソース](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)   
 [アイコンとカーソル: ディスプレイ デバイスのイメージ リソース](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)
