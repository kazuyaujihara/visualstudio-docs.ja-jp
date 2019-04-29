---
title: Hello World の拡張機能のチュートリアル |Microsoft Docs
ms.date: 03/14/2019
ms.topic: conceptual
ms.assetid: f74e1ad1-1ee5-4360-9bd5-d82467b884ca
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3beedce039d1c093b5dfebce07b09d7d3a5795dc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62912311"
---
# <a name="create-your-first-extension-hello-world"></a>初めての拡張機能を作成します。Hello World

この Hello World の例では、Visual Studio の初めての拡張機能の作成手順について説明します。 このチュートリアルでは、Visual Studio に新しいコマンドを追加する方法を示します。

学習方法は以下の手順となります。

* **[機能拡張プロジェクトの作成](#create-an-extensibility-project)**
* **[カスタム コマンドの追加](#add-a-custom-command)**
* **[ソース コードを変更](#modify-the-source-code)**
* **[実行](#run-it)**

この例ではVisual C#を使用して次に示すような「Say Hello World!」という名前のカスタム メニュー ボタンを追加します。 次に示します。

![Hello World コマンド](media/hello-world-say-hello-world.png)

> [!NOTE]
> この記事は、Windows 上の Visual Studio に適用されます。 Visual Studio for Mac では、次の[Visual Studio for Mac での拡張機能のチュートリアル](/visualstudio/mac/extending-visual-studio-mac-walkthrough) を参照してください。

## <a name="prerequisites"></a>必須コンポーネント

開始する前にインストールされている確認、 **Visual Studio 拡張機能の開発**ワークロードでは、VSIX のテンプレートが必要し、サンプル コードが含まれています。

> [!NOTE]
> Visual Studio 機能拡張プロジェクトを作成するには、Visual Studio の任意のエディション(Community、Professional、または Enterprise)を使用することができます。

## <a name="create-an-extensibility-project"></a>機能拡張プロジェクトの作成

::: moniker range="vs-2017"

手順 1. **[ファイル]** メニューで、**[新規作成]**、 > **[プロジェクト]** の順に作成します。

手順 2. 右上にある検索ボックスに "vsix"を入力し、ビジュアルを選択C# **VSIX プロジェクト**します。 "HelloWorld"を入力、**名前**クリックし、ダイアログの下部にある**OK**します。

![新しいプロジェクト](media/hello-world-new-project.png)

はじめに *Getting Started* ページといくつかのサンプル リソースが表示されます。

このチュートリアルを終了した後に再開する必要がある場合、 **スタート ページ** の **最近** セクションで HelloWorld プロジェクトを見つけられます。

::: moniker-end

::: moniker range=">=vs-2019"

手順 1. **[ファイル]** メニューで、**[新規作成]**、 > **[プロジェクト]** の順に作成します。 "Vsix"を検索し、ビジュアルを選択します。 C# **VSIX プロジェクト**し**次**します。

手順 2. "HelloWorld"を入力、**プロジェクト名**選択**作成**します。

![新しいプロジェクト](media/hello-world-new-project-2019.png)

HelloWorld プロジェクトで表示する必要があります**ソリューション エクスプ ローラー**します。

::: moniker-end

## <a name="add-a-custom-command"></a>カスタム コマンドの追加

手順 1. 選択した場合、 *.vsixmanifest*マニフェスト ファイルは、どのようなオプションは変更可能な説明、作成者、およびバージョンなどを参照してください。

手順 2. (ソリューションではなく) プロジェクトを右クリックします。 コンテキスト メニューで、次のように選択します。**追加**、し**新しい項目の**します。

手順 3. 選択、**拡張**セクションを選び、**カスタム コマンド**。

手順 4. **名前**下部にあるフィールドに、ファイル名を入力します。 *Command.cs*します。

![カスタム コマンド](media/hello-world-custom-command.png)

新しいコマンド ファイルが表示**ソリューション エクスプ ローラー**します。 で、**リソース**ノードで、コマンドに関連するその他のファイルを検索します。 たとえば、イメージを変更する場合は、PNG ファイルはここでは。

## <a name="modify-the-source-code"></a>ソース コードの変更

コマンドとボタンのテキストでの自動生成されたはこの時点では、非常に興味深いではないとします。 変更する場合は、VSCT ファイルと CS ファイルを変更できます。

* VSCT ファイルはコマンドの名前の変更だけでなく、Visual Studioのコマンドシステムでの場所を定義します。 VSCT ファイルを探索するときは、VSCT コード コントロールの各セクションで説明するコメントが表示されます。

* CS ファイルでは、クリック ハンドラーなどのアクションを定義できます。

::: moniker range="vs-2017"

手順 1. **ソリューション エクスプローラー**内で新規作成したコマンドの VSCT ファイルを検索します。 今回の場合は*CommandPackage.vsct*となっています。

![コマンドのパッケージ vsct](media/hello-world-command-package-vsct.png)

::: moniker-end

::: moniker range=">=vs-2019"

手順 1. **ソリューション エクスプ ローラー**、VS 拡張機能パッケージの VSCT ファイルを検索します。 呼び出されるこの場合、 *HelloWorldPackage.vsct*します。

::: moniker-end

手順 2. `ButtonText`パラメーターを`Say Hello World!`に変更します。

```xml
  ...
  <Button guid="guidCommandPackageCmdSet" id="CommandId" priority="0x0100" type="Button">
     <Parent guid="guidCommandPackageCmdSet" id="MyMenuGroup" />
     <Icon guid="guidImages" id="bmpPic1" />
     <Strings>
        <ButtonText>Say Hello World!</ButtonText>
     </Strings>
  </Button>
  ...
```

手順 3. **ソリューション エクスプ ローラー**に戻って、*Command.cs*ファイルを探します。 `Execute`メソッドでは、文字列を変更`message`から`string.Format(..)`に`Hello World!`します。

```csharp
  ...
  private void Execute(object sender, EventArgs e)
  {
    ThreadHelper.ThrowIfNotOnUIThread();
    string message = "Hello World!";
    string title = "Command";

    // Show a message box to prove we were here
    VsShellUtilities.ShowMessageBox(
        this.ServiceProvider,
        message,
        title,
        OLEMSGICON.OLEMSGICON_INFO,
        OLEMSGBUTTON.OLEMSGBUTTON_OK,
        OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST);
  }
  ...
```

各ファイルの変更が保存されているか確認してください。

## <a name="run-it"></a>実行

Visual Studio の実験用インスタンスでソース コードを実行できます。

手順 1. キーを押して**F5**を実行する、**デバッグの開始**コマンド。 このコマンドは、プロジェクトをビルドしと呼ばれる Visual Studio の新しいインスタンスを起動するデバッガーを起動、**実験用インスタンス**します。

::: moniker range="vs-2017"

Visual Studioのタイトル バーには**実験的なインスタンス**と表示されます。

![実験的なインスタンスのタイトル バー](media/hello-world-exp-instance.png)

::: moniker-end

手順 2. **ツール**のメニュー、**実験用インスタンス**、 をクリックして**Say Hello World!** します。

![最終的な結果](media/hello-world-final-result.png)

新規作成したカスタム コマンドからの出力、この場合では画面の中央のダイアログ ボックスに **Hello World!** メッセージが表示されます。

## <a name="next-steps"></a>次の手順

Visual Studio 拡張機能 の作業の基礎を知ることができたので、以下でさらに学習ができます。

* [Visual Studio 拡張機能の開発を始める](starting-to-develop-visual-studio-extensions.md)-サンプル、チュートリアル。 拡張機能を公開
* [新機能については、Visual Studio 2017 SDK](what-s-new-in-the-visual-studio-2017-sdk.md) -Visual Studio 2017 での新しい拡張機能
* [新機能については、Visual Studio 2019 SDK](whats-new-visual-studio-2019-sdk.md) -Visual Studio 2019 で新しい拡張機能
* [Visual Studio SDK の内部](internals/inside-the-visual-studio-sdk.md)-Visual Studio 機能拡張の詳細を説明します。