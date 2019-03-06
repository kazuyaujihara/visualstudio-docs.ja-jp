---
title: スタートアップ エクスペリエンスを変更する
ms.date: 02/01/2017
ms.topic: conceptual
f1_keywords:
- vs.ToolsOptionsPages.Startup
helpviewer_keywords:
- Start Page [Visual Studio]
- customizing Start Page [Visual Studio]
- Visual Studio Start Page
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c15824ec28547cbdb18fdfebc4ebcee1bdd1d387
ms.sourcegitcommit: cea6187005f8a0cdf44e866a1534a4cf5356208c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2019
ms.locfileid: "56953383"
---
# <a name="customize-startup"></a>スタートアップをカスタマイズする

Visual Studio のスタートアップ エクスペリエンスは何種類かの方法でカスタマイズできます。たとえば、ご利用の最新のソリューションを開いたり、単に空の展開環境を開いたりしてそれを行います。

::: moniker range="vs-2017"

また、カスタム スタート ページを表示することもできます。これは、ツール ウィンドウで実行される Windows Presentation Foundation (WPF) の XAML ページで、Visual Studio 内のコマンドを実行できます。

::: moniker-end

## <a name="to-change-the-startup-item"></a>スタートアップ アイテムを変更する

1. メニュー バーの **[ツール]**  >  **[オプション]** の順にクリックします。

2. **[環境]** を展開し、**[スタートアップ]** を選びます。

::: moniker range="vs-2017"

3. **[At startup]\(スタートアップ時\)** リストで、Visual Studio の起動後に表示するアイテムを選択します。

::: moniker-end

::: moniker range=">=vs-2019"

3. **[On startup, open]\(起動時に開く\)** リストで、Visual Studio の起動後に実行されるようにする動作を選択します。 **スタート ウィンドウ** (新しいプロジェクトまたは既存のプロジェクトを開くことができます)、**最新のソリューション**、または**空の環境**から選択します。

::: moniker-end

::: moniker range="vs-2017"

## <a name="to-show-a-custom-start-page"></a>カスタム スタート ページを表示する

Visual Studio SDK を使用して[独自のカスタム スタート ページを作成する](../extensibility/creating-a-custom-start-page.md)か、他のユーザーが既に作成したカスタム スタート ページを利用できます。 たとえば、[Visual Studio Marketplace](https://marketplace.visualstudio.com/search?target=VS&category=Tools&vsVersion=&subCategory=Start%20Pages&sortBy=Downloads) でカスタム スタート ページを検索できます。

カスタム スタート ページをインストールするには、*.vsix* ファイルを開くか、スタート ページ ファイルをコピーしてコンピューターの *%USERPROFILE%\ドキュメント\Visual Studio 2017\StartPages* フォルダーに貼り付けます。

### <a name="to-select-which-custom-start-page-to-display"></a>表示するカスタム スタート ページを選択する

1. メニュー バーで、**[ツール]**>**[オプション]** の順に選択します。

1. **[環境]** を展開し、**[スタートアップ]** を選びます。

1. **[スタート ページのカスタマイズ]** の一覧で、使用するページを選択します。

> [!TIP]
> カスタム スタート ページのエラーによって Visual Studio がクラッシュする場合、セーフ モードで Visual Studio を起動し、既定のスタート ページを使用するように設定します。 「[/SafeMode (devenv.exe)](../ide/reference/safemode-devenv-exe.md)」をご覧ください。

## <a name="see-also"></a>関連項目

- [Visual Studio IDE のカスタマイズ](../ide/personalizing-the-visual-studio-ide.md)

::: moniker-end