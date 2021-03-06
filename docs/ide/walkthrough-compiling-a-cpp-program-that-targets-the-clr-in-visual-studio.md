---
title: "チュートリアル: Visual Studio で CLR をターゲットにした C++ プログラムのコンパイル | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コマンド ライン アプリケーション [C++], マネージ コード"
  - "コンパイル (プログラムを) [C++]"
  - "マネージ コード [C++]"
  - "Visual C++, マネージ コード"
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
caps.latest.revision: 40
caps.handback.revision: 40
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# チュートリアル: Visual Studio で CLR をターゲットにした C++ プログラムのコンパイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.NET クラスを使用する Visual C\+\+ プログラムを作成し、そのプログラムを Visual Studio 開発環境でコンパイルできます。  
  
 次の処理手順では、独自の Visual C\+\+ プログラムを入力することも、いずれかのサンプル プログラムを使用することもできます。  この処理手順で使用するサンプル プログラムは、textfile.txt という名前のテキスト ファイルを作成し、それをプロジェクト ディレクトリに保存します。  
  
## 必須コンポーネント  
 このトピックは、C\+\+ 言語の基本を理解していることを前提としています。  
  
### Visual Studio で新しいプロジェクトを作成し、新しいソース ファイルを追加するには  
  
1.  新しいプロジェクトを作成します。  **\[ファイル\]** メニューの **\[新規作成\]** をポイントし、**\[プロジェクト\]** をクリックします。  
  
2.  Visual C\+\+ のプロジェクトの種類で **\[CLR\]** をクリックし、**\[空の CLR プロジェクト\]** をクリックします。  
  
3.  プロジェクト名を入力します。  
  
     既定では、プロジェクトを含むソリューションは新しいプロジェクトと同じ名前になりますが、別の名前を入力してもかまいません。  必要に応じて、プロジェクトの場所として別の場所を入力できます。  
  
     **\[OK\]** をクリックして、新しいプロジェクトを作成します。  
  
4.  ソリューション エクスプローラーが表示されていない場合は、**\[表示\]** メニューの **\[ソリューション エクスプローラー\]** をクリックします。  
  
5.  プロジェクトに新しいソース ファイルを追加します。  
  
    -   ソリューション エクスプローラーで **\[ソース ファイル\]** フォルダーを右クリックし、**\[追加\]** をポイントして、**\[新しい項目\]** をクリックします。  
  
    -   **\[C\+\+ ファイル \(.cpp\)\]** をクリックし、ファイル名を入力して、**\[追加\]** をクリックします。  
  
     **.cpp** ファイルがソリューション エクスプローラーの **\[ソース ファイル\]** フォルダーに表示されます。また、タブ付きウィンドウには、このファイルに必要なコードを入力する場合の入力位置が表示されます。  
  
6.  Visual Studio で新しく作成されたタブ内をクリックし、有効な Visual C\+\+ プログラムを入力するか、いずれかのサンプル プログラムをコピーして貼り付けます。  
  
     たとえば、\(プログラミング ガイドの **\[File Handling and I\/O\]** ノードにある\) [方法: テキスト ファイルを記述する](../Topic/How%20to:%20Write%20a%20Text%20File%20\(C++-CLI\).md) サンプル プログラムを使用できます。  
  
     サンプル プログラムを使用する場合は、.NET オブジェクトを作成する際に `new` キーワードではなく、`gcnew` ``  キーワードを使用する点に注意してください。また、`gcnew` が返すのはポインター \(`*`\) ではなく、ハンドル \(`^`\) である点にも注意してください。  
  
     `StreamWriter^ sw = gcnew StreamWriter(fileName);`  
  
     新しい Visual C\+\+ 構文の詳細については、「[Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)」を参照してください。  
  
7.  **\[ビルド\]** メニューの **\[ソリューションのビルド\]** をクリックします。  
  
     **\[出力\]** ウィンドウに、ビルド ログの場所やビルドの状態を示すメッセージなど、コンパイルの進行状況に関する情報が表示されます。  
  
     プログラムに変更を加えた後、ビルドを行わずにプログラムを実行すると、ダイアログ ボックスはプロジェクトが古いものであることを示す場合があります。  Visual Studio でアプリケーションをビルドするたびに確認メッセージを表示する代わりに、常に現在のバージョンのファイルを使用する場合は、このダイアログ ボックスのチェック ボックスをオンにしてから **\[OK\]** をクリックします。  
  
8.  **\[デバッグ\]** メニューの **\[デバッグなしで開始\]** をクリックします。  
  
9. サンプル プログラムを使用している場合は、プログラムを実行するとテキスト ファイルが作成されたことを示すコマンド ウィンドウが表示されます。  任意のキーを押してコマンド ウィンドウを閉じます。  
  
     **textfile.txt** という名前のテキスト ファイルがプロジェクト ディレクトリに作成されています。  このファイルはメモ帳で開くことができます。  
  
    > [!NOTE]
    >  空の CLR プロジェクト テンプレートを選択すると、**\/clr** コンパイラ オプションが自動的に設定されます。  これを確認するには、**ソリューション エクスプローラー**でプロジェクトを右クリックし、**\[プロパティ\]** をクリックして、**\[構成プロパティ\]** の **\[全般\]** ノード内にある **\[共通言語ランタイム サポート\]** チェック ボックスをオンにします。  
  
## 次の内容  
 **前へ :** [チュートリアル: コマンド ラインでのネイティブ C\+\+ プログラムのコンパイル](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md) &#124; **次へ :** [チュートリアル: コマンド ラインでの C プログラムのコンパイル](../Topic/Walkthrough:%20Compiling%20a%20C%20Program%20on%20the%20Command%20Line.md)  
  
## 参照  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ja-jp/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C\/C\+\+ プログラムのビルド](../build/building-c-cpp-programs.md)