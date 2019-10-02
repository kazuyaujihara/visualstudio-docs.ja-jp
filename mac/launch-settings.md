---
title: launchSettings.json のサポート
description: このドキュメントでは、Visual Studio for Mac での launchSettings.json のサポートについて説明します
author: sayedihashimi
ms.author: sayedha
ms.date: 09/18/2019
ms.assetid: a556f9d7-86a8-408e-aa54-392584845889
ms.openlocfilehash: e7de368dd26bf2724a7bc060dade46422817da1e
ms.sourcegitcommit: ea182703e922c74725045afc251bcebac305068a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71213817"
---
# <a name="launchsettingsjson"></a>launchSettings.json

ASP.NET Core プロジェクトを開発するときは、`launchSettings.json` ファイルの内容をカスタマイズすることで、開発シナリオ内でプロジェクトを開始する方法を構成できます。 Visual Studio for Mac では、プロジェクト オプション UI を使用するか、`launchSettings.json` ファイルを直接編集することで、このファイルを更新できます。 このファイルは、Windows 上で Visual Studio を実行する場合、または `dotnet` を使用してコマンド ラインから実行する場合に使用できる構成ファイルと同じです。 このファイルは、プロジェクトの `Properties` フォルダーの下に保存されます。

詳細については、「[ASP.NET Core で複数の環境を使用する](https://docs.microsoft.com/aspnet/core/fundamentals/environments)」を参照してください。 このドキュメントでは、Visual Studio for Mac でこのファイルを更新する方法について説明します。

## <a name="updating-start-configuration-using-visual-studio-for-mac"></a>Visual Studio for Mac を使用して開始構成を更新する

Visual Studio for Mac で `launchSettings.json` を直接編集することも、プロジェクト オプションを使用して編集することもできます。 プロジェクト オプションを表示するには、プロジェクトを右クリックし、[オプション] を選択します。 下の画像を参照してください。

![選択されたプロジェクト コンテキスト メニュー オプション](media/vsmac-ctx-proj-options.png)

このダイアログが表示されたら、[実行] > [構成] > [既定] の順に移動します。

![既定の構成を実行する](media/vsmac-run-config-default.png)

ここで構成するものは、主に 2 つあります。

 - 開始時に設定される環境変数
 - プロジェクトの開始 URL

## <a name="configure-environment-variables"></a>環境変数を構成する

グリッドを使用して、環境変数の値を指定することができます。 これらの環境変数は、Visual Studio for Mac 内でアプリケーションを起動するときに設定されます。 ASP.NET Core アプリケーションを開発する場合は、特殊な `ASPNETCORE_ENVIRONMENT` 環境変数に注意する必要があります。 詳細については、「[ASP.NET Core で複数の環境を使用する](https://docs.microsoft.com/aspnet/core/fundamentals/environments)」を参照してください。


## <a name="configure-start-url"></a>開始 URL を構成する

アプリケーションの起動に使用する URL を構成するには、[ASP.NET Core] タブにアクセスします。

![proj オプションの開始 url](media/vsmac-run-config-default-aspnetcore.png)

ここでは、アプリケーションによって、その開始時にリッスンされる URL を指定できます。