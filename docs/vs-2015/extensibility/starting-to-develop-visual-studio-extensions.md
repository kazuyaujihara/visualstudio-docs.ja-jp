---
title: 拡張機能の開発を始める |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- getting started, Visual Studio integration
- Visual Studio, integration
ms.assetid: 8fe5e2ab-a424-4173-9d39-dd082c4d58d0
caps.latest.revision: 30
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6d8050ea7447a67f50f42157d57c17d3f1f8a329
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68160590"
---
# <a name="starting-to-develop-visual-studio-extensions"></a>Visual Studio 拡張機能の開発を始める
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

前に Visual Studio 拡張機能を初めて作成する場合、いくつか質問がある可能性があります。 ここで、最も一般的なものの一部を示しています。 探している情報が表示されない場合は、フィードバック ボタンを使用して (**このページに立ちましたか?** 画面の下部にある) する情報を確認します。

## <a name="what-software-do-i-need-to-develop-visual-studio-extensions"></a>Visual Studio 拡張機能を開発するために必要なソフトウェアはなんですか。
 Visual Studio 拡張機能を開発するために Visual Studio 2015 だけでなく、Visual Studio 2015 SDK をインストールする必要があります。   通常のセットアップの一部として、Visual Studio 2015 SDK をインストールすることができますか、後でインストールできます。 Visual Studio SDK のインストールに関する詳細は、次の [Visual Studio SDK](../extensibility/visual-studio-sdk.md) を参照してください。

## <a name="what-kinds-of-things-can-i-do-with-visual-studio-extensions"></a>Visual Studio 拡張機能でどのような種類の項目を行えるのでしょうか？
 無限の可能性に関してはさまざまな Visual Studio 拡張機能を考えたときに制限します。 もちろん、ほとんどの拡張機能がある問題、コードの記述であることが、大文字と小文字をする必要はありません。 拡張機能作成のいくつかの例を次に示します。

- 構文の色分け、IntelliSense、コンパイラとデバッグのサポートと、Visual Studio に含まれていない言語のサポート

- 追加のテンプレート、コードのリファクタリング、新しいダイアログ ボックスまたはツール ウィンドウを使用したIDE の利便性を拡張させる生産性向上ツール。

- データのデザインまたはクラウドのサポートなどのシナリオのドメイン固有のデザイナー

  拡張機能の例については、[Visual Studio Marketplace](https://marketplace.visualstudio.com/)を参照してください。 見ても行う[Visual Studio のオープン ソース Extensions](https://github.com/Microsoft/extendvs/blob/master/CommunityExtensions.md)します。

## <a name="which-visual-studio-features-can-i-extend"></a>Visual Studio 機能を拡張できますか？
 理論上は、Visual Studio のあらゆる部分を拡張することができます: メニューのツールバー、コマンド、windows、ソリューション、プロジェクト、エディターなど。

 実際には、ほとんどの人が望んでいる機能は、コマンド、メニューとツールバー、windows、IntelliSense、およびプロジェクトの拡張機能で見つかります。 関連するセクションへのリンクを次に示します。

- [メニューとコマンドの拡張](../extensibility/extending-menus-and-commands.md): Visual Studio メニューおよびツールバーに独自の項目を追加します。 Visual Studio の新機能または独自の外部ヘルパー アプリケーションの起動に使用できます。 メニュー項目のカスタム ショートカットを指定することもできます。

- [拡張とカスタマイズ ツール Windows](../extensibility/extending-and-customizing-tool-windows.md): 既存のツール ウィンドウを拡張または独自のツール ウィンドウを作成します。 たとえば複数の**プロパティ**を持つものに新しいプロパティを追加したり、追加機能を追加した新しいツール ウィンドウを作成したりできます。

- [エディターと言語サービスの拡張機能](../extensibility/editor-and-language-service-extensions.md): Visual Studio の言語に対して IntelliSense が提供する独自のカスタマイズを追加するか、新しいプログラミング言語のサポートを作成します。 新しいステートメント入力候補、提案、および新しいクイックヒントのツールチップ表示を作成することができます。 電球アイコンから、新しいプログラミング言語をサポートするためにリファクタリングの提案を追加したり、コード修正プログラムを追加したりすることができます。

- [プロジェクトの拡張](../extensibility/extending-projects.md)

- [ユーザー設定とオプションの拡張](../extensibility/extending-user-settings-and-options.md)

- [プロパティとプロパティ ウィンドウの拡張](../extensibility/extending-properties-and-the-property-window.md)

- [Visual Studio の他の部分の拡張](../extensibility/extending-other-parts-of-visual-studio.md)

- [Visual Studio の分離シェル](../extensibility/visual-studio-isolated-shell.md)

## <a name="BKMK_ProjectTemplate"></a> VSSDK によってどのようなプロジェクト テンプレートが提供されますか？
 2 つの主な種類の拡張機能は、VSPackage および MEF 拡張機能です。 一般に、VSPackage 拡張機能はコマンド、ツール ウィンドウ、およびプロジェクトを拡張する場合に使用されます。 MEF 拡張機能は、拡張、または Visual Studio エディターのカスタマイズに使用されます。

 Visual C# および Visual Basic の拡張機能の場合、VSSDK には、メニュー コマンド、ツール ウィンドウおよびエディターの拡張機能を作成する新しい項目テンプレートと共に使用できる空の VSIX プロジェクト テンプレートが用意されています。 詳細については、次を参照してください。 [、Visual Studio 2015 SDK の新](../extensibility/what-s-new-in-the-visual-studio-2015-sdk.md)します。 パッケージ プロジェクト テンプレート、コード スニペット、およびその他の成果物を他のユーザーに配布するために、このテンプレートを使用することもできます。

 C++ の場合は、VSPackage のウィザードは、メニュー コマンド、ツール ウィンドウ、およびカスタム エディターを追加するコードが用意されています。

 分離シェル テンプレートは、ブランド化して独自として配布する Visual Studio シェルのバージョンの拡張機能をパッケージ化するために使用されます。 次のトピックでは、それぞれの種類の拡張機能を使用する方法を示します。

- メニュー コマンド。[メニュー コマンドを使用した拡張機能の作成](../extensibility/creating-an-extension-with-a-menu-command.md)

- ツール ウィンドウ:[ツール ウィンドウでの拡張機能の作成](../extensibility/creating-an-extension-with-a-tool-window.md)

- エディターの拡張機能:[エディターの項目テンプレートを使用した拡張機能の作成](../extensibility/creating-an-extension-with-an-editor-item-template.md)

- 基本的な Vspackage は:[VSPackage を使用した拡張機能の作成](../extensibility/creating-an-extension-with-a-vspackage.md)

- VSIX プロジェクト テンプレート:[VSIX プロジェクトのテンプレートの概要](../extensibility/getting-started-with-the-vsix-project-template.md)

- Visual Studio の分離シェル。[チュートリアル: 基本的な分離シェル アプリケーションを作成する](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)

## <a name="how-do-i-get-my-extension-to-look-like-visual-studio"></a>私の拡張をVisual Studio のように見せる方法はありますか？
 拡張機能の UI を設計するための便利なヒントを取得[Visual Studio ユーザー エクスペリエンス ガイドライン](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md)します。

## <a name="where-can-i-find-examples-of-vssdk-code"></a>VSSDK のコードの例についてはどこで確認できますか？
 前のセクションに記載のリンクは、ある特定の機能を実装する方法を説明するチュートリアルです。 GitHub の [Visual Studio のサンプル](https://aka.ms/vs2015sdksamples) でオープン ソースの VSSDK のサンプルを見つけることができます。

## <a name="how-can-i-distribute-my-extension"></a>私の拡張機能を配布する方法は?
 別のコンピューターにあなたの拡張機能をインストールするか、ダブルクリックするとインストールできる.vsix ファイルを友人に送信することができます。 VSIX パッケージの詳細については [Visual Studio 拡張機能の配布](../extensibility/shipping-visual-studio-extensions.md) を参照してください。

 多数の Visual Studio の顧客を可視化、Visual Studio ギャラリーで、拡張機能を公開することもできます。 ギャラリーの拡張機能をパッケージ化の例は、次を参照してください。[チュートリアル。Visual Studio 拡張機能を公開](../extensibility/walkthrough-publishing-a-visual-studio-extension.md)します。 ギャラリーに発行するために必要があるについての詳細については、次を参照してください。[製品と Visual Studio の拡張機能](https://visualstudiogallery.msdn.microsoft.com/)します。
