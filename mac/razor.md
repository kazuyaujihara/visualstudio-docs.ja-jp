---
title: Razor
description: Visual Studio for Mac の asp.net core アプリの Razor サポートに関する情報
author: sayedihashimi
ms.author: sayedha
ms.date: 05/03/2018
ms.technology: vs-ide-general
ms.assetid: F898CB6E-05ED-44CD-8DB6-427B2592CCC6
ms.openlocfilehash: a66a31d2c63fcb0e2adc4554c49a76c727f9a288
ms.sourcegitcommit: cf8c0fef2b9690595e99ce3802586cdd55fd37c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107927"
---
# <a name="razor"></a>Razor

Visual Studio for Mac には、 *.cshtml* ファイルでの IntelliSense や構文の強調表示など、Razor 編集のサポートが用意されています。

![Visual Studio for Mac での Razor 編集](media/razor-editor.png)

このガイドでは、最初の Razor Web アプリの作成に関する概要について説明します。 より詳細なガイドについては、[.NET Core ドキュメントの Razor Pages](/aspnet/core/razor-pages/index) をご参照ください。

## <a name="creating-a-new-razor-project"></a>新しい Razor プロジェクトの作成

* ようこそ画面で、 **[新規]** を選択して新しいプロジェクトを作成します。

![Visual Studio for Mac での新しいプロジェクト](media/razor-new.png)

* [新しいプロジェクト] ダイアログで、 **[.NET Core]**  >  **[アプリ]**  >  **[Web アプリケーション]** に移動し、 **[次へ]** ボタンをクリックします。

![Razor プロジェクト テンプレート](media/razor-new-project1.png)

* 必要な .NET Core ターゲット フレームワークを選択し (2.2 以降を推奨)、 **[次へ]** を選択します。  使用するプロジェクトの名前を選び、必要な場合は git サポートを追加します。 **[作成]** を選択してプロジェクトを作成します。

![Razor プロジェクト名](media/razor-new-project2.png)

Visual Studio for Mac により、お客様のプロジェクトがコード レイアウトで開かれます。

* **Cmd - Opt - F5** キーを使って、デバッグなしでプロジェクトを実行します

Visual Studio によって [Kestral](https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel) が起動されます。また、`https://localhost:5001` に対してブラウザーが起動され、最初の Razor Web アプリが表示されます。

![Safari での Razor Web アプリ](media/razor-webapp.png)

## <a name="project-anatomy"></a>プロジェクトの構造

Razor Web アプリは次のコンポーネントで構成されています。

### <a name="pages-folder"></a>Pages フォルダー

プロジェクト内の Pages フォルダーには、Web ページと、以下のそれぞれに関するコードビハインドが置かれます。
* HTML マークアップと Razor 構文のための * *.cshtml* ファイル。
* ページ イベントを処理するための C# コードビハインドの * *.cshtml.cs* ファイル。

サポート ファイルには、アンダー スコアで始まる名前が付けられます。 たとえば、_Layout.cshtml ファイルでは、すべてのページに共通の UI 要素が構成されます。 このファイルでは、ページの上部に表示されるナビゲーション メニューと、ページの下部に表示される著作権の通知が設定されます。 詳細については、「[ASP.NET Core でのレイアウト](https://docs.microsoft.com/aspnet/core/mvc/views/layout)」をご覧ください。

### <a name="launch-settings"></a>起動設定

*launchSettings.json* ファイルには、IIS 設定、アプリケーションの URL、およびその他の関連する設定が含まれています。

### <a name="app-settings"></a>アプリケーション設定

*appSettings,json* ファイルには、接続文字列などの構成データが含まれています。

構成について詳しくは、[ASP.NET での構成ガイド](https://docs.microsoft.com/aspnet/core/fundamentals/configuration/index)に関する記事をご覧ください。

### <a name="wwwroot-folder"></a>wwwroot フォルダー

HTML ファイル、JavaScript ファイル、CSS ファイルなどの静的ファイルが格納されます。 詳細については、「[ASP.NET Core の静的ファイル](https://docs.microsoft.com/aspnet/core/fundamentals/static-files)」をご覧ください。

### <a name="programcs"></a>Program.cs

プログラムのエントリ ポイントが保存されます。 詳細については、「[ASP.NET Core の Web ホスト](https://docs.microsoft.com/aspnet/core/fundamentals/host/web-host)」をご覧ください。

### <a name="startupcs"></a>Startup.cs

cookie に対する同意が必要かどうかなど、アプリの動作を構成するコードが保存されます。 詳細については、「[ASP.NET Core でのアプリケーションのスタートアップ](https://docs.microsoft.com/aspnet/core/fundamentals/startup)」をご覧ください。

## <a name="see-aso"></a>関連項目

Razor Web アプリの作成に関するより包括的なガイドについては、「[ASP.NET Core での Razor ページの概要](https://docs.microsoft.com/aspnet/core/razor-pages/index)」をご覧ください。
