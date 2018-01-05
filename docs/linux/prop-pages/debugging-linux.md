---
title: "デバッガー プロパティ (Linux C++)| Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c1c0fcc-a49b-451c-a5cb-ce9711fac064
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.RaspberryDebugger.DebuggerType
- VC.Project.IVCLocalDebugPageObject.CommandArguments
- VC.Project.IVCLocalDebugPageObject.WorkingDirectory
- VC.Project.RaspberryDebugger.LaunchActivity
- VC.Project.LinuxDebugger.DebugChildProcesses
ms.openlocfilehash: d47645eab33ffb0ee6a203fdfb0cf30c856ea63f
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="c-debugging-properties-linux-c"></a>C++ デバッグ プロパティ (Linux C++)

プロパティ | 説明 | オプション
--- | ---| ---
起動前コマンド | デバッグの開始前とデバッガーの実行前にシェルで実行されるコマンド。デバッグ環境に影響を与えるために使用できます。
プログラム | リモート システムでデバッグするためのプログラムの完全パス。 これはリモート システム上のパスです。 空のまま残すか、変更しなかった場合、既定値である現在のプロジェクト出力に戻ります。
プログラムの引数 | デバッグ中のプログラムに渡すコマンド ライン引数。
作業ディレクトリ | リモート アプリケーションの作業ディレクトリ。 既定では、ユーザーのホーム ディレクトリになります。
追加のデバッガー コマンド | デバッグを開始する前に実行するデバッガーに対する追加の gdb コマンド。
デバッガーのポート番号 | デバッガーがリモート デバッガーと通信するためのポート番号。 このポートはローカルで使用できません。 この値は 1 から 65535 までの正の数にする必要があります。 指定されない場合、空いているポート番号が使用されます。
リモート デバッガーのポート番号 | リモート システムでリモート デバッガー サーバー (gdbserver) が待ち受けるポート番号。 このポート番号はリモート システムで使用できません。 この値は 1 から 65535 までの正の数にする必要があります。 指定されない場合、4444 以降の番号で空いているポート番号が使用されます。
デバッグ モード | デバッガーと gdb の連携方法を指定します。 gdb モードで、リモート システムのシェルで gdb が実行されます。 gdbserver モードでは、gdb はローカルで実行され、リモート実行されている gdbserver に接続します。 | **gdbserver**<br>**gdb**<br>
追加のシンボル検索パス | デバッグ シンボルの追加の検索パス (solib-search-path)。
子プロセスのデバッグ | 子プロセスのデバッグを有効にするかどうかを指定します。
Python 整形出力を有効にする | 式の値の整形出力を有効にします。 gdb デバッグ モードでのみサポートされています。
視覚化ファイル | SLT 型の視覚化指令を含む既定のネイティブ視覚化ファイル (.natvis)。 現行のソリューションに属するその他の .natvis ファイルが自動的に読み込まれます。
追加のソース ファイル パスのマップ | デバッガーにとって追加のパスに相当するもので、Windows ソース ファイル名を Linux ソース ファイル名にマッピングするために使用されるパス。 形式は "\<windows-path>=\<linux-path>;..." です。 Windows パスの下にあるソース ファイル名は、Linux パスの下で相対的に同じ位置にあるとして参照されます。 ローカル プロジェクトに見つかるファイルは追加のマッピングを必要としません。