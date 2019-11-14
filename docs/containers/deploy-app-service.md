---
title: ASP.NET Core Docker コンテナーを Azure App Service にデプロイする | Microsoft Docs
description: Visual Studio コンテナー ツールを使用して、ASP.NET Core Web アプリを Azure App Service にデプロイする方法を説明します
author: ghogen
manager: jillfra
ms.technology: vs-azure
ms.devlang: dotnet
ms.topic: article
ms.date: 03/08/2019
ms.author: ghogen
ms.openlocfilehash: 5d1f160435fd8c62a44d3e5d3192870143558de4
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73188793"
---
# <a name="deploy-an-aspnet-core-container-to-azure-app-service-using-visual-studio"></a>Visual Studio を使用した Azure App Service への ASP.NET Core コンテナーのデプロイ

このチュートリアルでは、Visual Studio を使用し、コンテナー化された ASP.NET Core Web アプリケーションを [Azure App Service](/azure/app-service) に発行する方法について説明します。 Azure App Service は、Azure でホストされている単一コンテナー Web アプリに最適なサービスです。

Azure サブスクリプションをお持ちでない場合は、開始する前に [無料アカウント](https://azure.microsoft.com/free/dotnet/?utm_source=acr-publish-doc&utm_medium=docs&utm_campaign=docs) を作成してください。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するには、次のものが必要です。

::: moniker range="vs-2017"
- "ASP.NET および Web 開発" ワークロードと共に、最新バージョンの [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) をインストールする
::: moniker-end
::: moniker range=">=vs-2019"
- *[ASP.NET および Web の開発]* ワークロードを含む [Visual Studio 2019](https://visualstudio.microsoft.com/downloads)。
::: moniker-end
- [Docker Desktop](https://docs.docker.com/docker-for-windows/install/) のインストール

## <a name="create-an-aspnet-core-web-app"></a>ASP.NET Core Web アプリを作成する

次の手順では、このチュートリアルで使用する基本的な ASP.NET Core アプリの作成について説明します。

::: moniker range="vs-2017"
1. Visual Studio のメニューで、 **[ファイル]、[新規作成]、[プロジェクト]** の順に選択します。
2. **[新しいプロジェクト]** ダイアログ ボックスの **[テンプレート]** セクションで、 **[Visual C#]、[Web]** の順に選択します。
3. **[ASP.NET Core Web アプリケーション]** を選択します。
4. 新しいアプリケーションに名前を設定 (または、既定の名前をそのまま使用) して、 **[OK]** を選択します。
5. **[Web アプリケーション]** を選択します。
6. **[Docker サポートを有効にする]** チェック ボックスをオンにします。
7. コンテナーの種類に **[Linux]** を選択し、 **[OK]** をクリックします。 Windows コンテナーはコンテナーとして Azure App Service にデプロイできません。
::: moniker-end
::: moniker range=">= vs-2019"
1. Visual Studio の [スタート] ウィンドウから **[新しいプロジェクトの作成]** を選択します。
1. **[ASP.NET Core Web アプリケーション]** を選択し、 **[次へ]** を選択します。
1. 新しいアプリケーションに名前を設定 (または、既定の名前をそのまま使用) し、 **[作成]** を選択します。
1. **[Web アプリケーション]** を選択します。
1. **[HTTPS 用の構成]** チェックボックスを使用し、SSL サポートを使用するかどうかを選択します。
1. **[Docker サポートを有効にする]** チェック ボックスをオンにします。
1. コンテナーの種類に **[Linux]** を選択し、 **[作成]** をクリックします。 Windows コンテナーはコンテナーとして Azure App Service にデプロイできません。
::: moniker-end

## <a name="deploy-the-container-to-azure"></a>コンテナーを Azure にデプロイする

1. **ソリューション エクスプローラー**で対象のプロジェクトを右クリックし、 **[発行]** を選択します。
1. 発行先ダイアログで、 **[App Service Linux]** を選択します。
1. App Service にのみ発行するか、App Service と Azure Container Registry (ACR) の両方に発行できます。 Azure Container Registry (ACR) でコンテナーを発行するには、 **[Create new App Service for containers]\(コンテナー用に新しい App Service を作成する\)** を選択し、 **[発行]** をクリックします。

   ![発行ダイアログのスクリーンショット](media/deploy-app-service/publish-app-service-linux.PNG)

   Azure Container Registry を使用せずに Azure App Service にのみ発行するには、 **[新規作成]** を選択し、 **[発行]** をクリックします。

1. Azure サブスクリプションに関連付けられているアカウントでサインインしていることを確認し、一意の名前、サブスクリプション、リソース グループ、ホスティング プラン、コンテナー レジストリ (該当する場合) を選択するか、既定値をそのまま選択します。

   ![発行設定のスクリーンショット](media/deploy-app-service/publish-app-service-linux2.png)

1. **[作成]** を選択します。 選択したリソース グループとコンテナー レジストリでコンテナーが Azure にデプロイされます。 このプロセスには時間が少しばかりかかります。 完了すると、 **[発行]** タブにサイトの URL など、発行したものに関する情報が表示されます。

   ![発行タブのスクリーンショット](media/deploy-app-service/publish-succeeded.PNG)

1. サイト リンクをクリックし、Azure でアプリが想定どおりに動作することを確認します。

   ![Web アプリケーションのスクリーンショット](media/deploy-app-service/web-application-running.png)

1. リソース グループやコンテナー レジストリなど、選択したすべての詳細が含まれる発行プロファイルが保存されます。
1. 同じ発行プロファイルでもう一度デプロイするには、 **[発行]** ボタンか **[Web 発行アクティビティ]** ウィンドウの **[発行]** ボタンを使用するか、**ソリューション エクスプローラー**でプロジェクトを右クリックし、コンテキストメニューで **[発行]** 項目を選択します。

## <a name="clean-up-resources"></a>リソースをクリーンアップする

このチュートリアルに関連付けられている Azure リソースをすべて削除するには、[Azure portal](https://portal.azure.com) を使用してリソース グループを削除します。 発行した Web アプリケーションに関連付けられているリソース グループを見つけるには、 **[表示]** 、 **[その他のウィンドウ]** 、 **[Web 発行アクティビティ]** の順に選択し、歯車アイコンを選択します。 **[発行]** タブが開きます。これにはリソース グループが含まれています。

Azure portal で **[リソース グループ]** をクリックし、リソース グループを選択してその詳細ページを開きます。 リソース グループが間違っていないことを確認し、 **[リソース グループの削除]** を選択し、名前を入力し、 **[削除]** を選択します。

## <a name="next-steps"></a>次の手順

[Azure Pipelines](/azure/devops/pipelines/?view=azure-devops) を使用して、継続的インテグレーションおよび継続的配信 (CI/CD) を設定します。

## <a name="see-also"></a>関連項目

[Azure Container Registry へのデプロイ](hosting-web-apps-in-docker.md)