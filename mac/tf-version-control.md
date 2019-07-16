---
title: Team Foundation バージョン管理 (TFVC)
description: Team Foundation バージョン管理 (TFVC) を利用して、Visual Studio for Mac から Team Foundation Server/Azure DevOps に接続します。
author: jmatthiesen
ms.author: jomatthi
ms.date: 06/25/2019
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: 378d1eaf1d57818a976f41a81c1098d75bb12e48
ms.sourcegitcommit: 7fbfb2a1d43ce72545096c635df2b04496b0be71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "67691949"
---
# <a name="connecting-to-team-foundation-version-control"></a>Team Foundation バージョン管理に接続する

> [!NOTE]
> macOS 上での最善のバージョン管理エクスペリエンスのためには、Team Foundation バージョン管理ではなく Git を使用することをお勧めします。 Visual Studio for Mac では Git がサポートされており、Team Foundation Server (TFS)/Azure DevOps にホストされているリポジトリでの既定のオプションです。 TFS/Azure DevOps での Git の使用について詳しくは、「[Git リポジトリのセットアップ](/visualstudio/mac/set-up-git-repository)」の記事をご覧ください。
> 
> 以前に Visual Studio for Mac の TFVC 拡張機能のプレビュー リリースをご使用だった場合、これは Visual Studio 2019 for Mac ではサポートされなくなります。

Azure Repos では、バージョン管理の 2 つのモデルを提供しています。分散バージョン管理システムの [Git](/azure/devops/repos/git/?view=azure-devops) と、集中バージョン管理システムの [Team Foundation バージョン管理](/azure/devops/repos/tfvc/index?view=azure-devops) (TFVC) です。

Visual Studio for Mac では、Git リポジトリに対して完全なサポートを提供していますが、TFVC を利用するにはいくつかの回避策が必要になります。 現在、バージョン管理に TFVC を使用している場合は、TFVC にホストされているソース コードにアクセスするために、いくつかのソリューションを使用できます。

* [グラフィカル UI の場合、Visual Studio Code と Azure Repos 拡張機能を使用する](#use-visual-studio-code-and-the-azure-repos-extension)
* [Team Explorer Everywhere Command Line Client (TEE-CLC) を使用してお使いのリポジトリに接続する](#connecting-using-the-team-explorer-everywhere-command-line-client)

以降、この記事では、上記の一覧に示したオプションについて説明していきます。

## <a name="requirements"></a>必要条件

* Visual Studio Community、Professional、Enterprise for Mac バージョン 7.8 以降。
* Azure DevOps Services、Team Foundation Server 2013 以降、または Azure DevOps Server 2018 以降。
* Team Foundation バージョン管理を使用して構成された、Azure DevOps Services または Team Foundation Server/Azure DevOps Server 内のプロジェクト。

## <a name="use-visual-studio-code-and-the-azure-repos-extension"></a>Visual Studio Code と Azure Repos 拡張機能を使用する

グラフィカル インターフェイスを操作してバージョン管理内のファイルを管理する場合、Visual Studio Code 対応の Azure Repos 拡張機能では、Microsoft からサポートされているソリューションを提供しています。 使用を開始するには、[Visual Studio Code](https://code.visualstudio.com) をダウンロードして、[Azure Repos 拡張機能を構成する](https://marketplace.visualstudio.com/items?itemName=ms-vsts.team)方法を確認します。

## <a name="connecting-using-the-team-explorer-everywhere-command-line-client"></a>Team Explorer Everywhere Command Line Client (TEE-CLC) を使用して接続する

macOS ターミナルを快適に使用している場合、Team Explorer Everywhere Command Line Client (TEE-CLC) では、TFVC 内のソースに接続するためのサポートされた方法を提供しています。

以下の手順に従って、TFVC への接続を設定し変更をコミットできます。

### <a name="setting-up-the-tee-clc"></a>TEE-CLC のセットアップ

TEE CLC のセットアップを行うには、2 つの方法があります。

* Homebrew を使用してクライアントをインストールする
* クライアントをダウンロードして手動でインストールする

最も簡単なソリューションは、macOS 用のパッケージ マネージャーである **HomeBrew を使用する**ことです。 この方法を使用してインストールするには、次の手順を実行します。

1. macOS ターミナルのアプリケーションを起動します。
1. ターミナルと [Homebrew ホーム ページ](https://brew.sh/)上の手順を使用して、Homebrew をインストールします。
1. Homebrew がインストールされたら、ご利用のターミナルから次のコマンドを実行します。`brew install tee-clc`

**TEE-CLC を手動でセットアップするには**:

1. Team Explorer Everywhere GitHub リポジトリのリリース ページから [ の最新バージョンをダウンロード](https://github.com/Microsoft/team-explorer-everywhere/releases)します (例えば、この記事の執筆時点では tee-clc-14.134.0.zip)。
1. .zip の内容をディスク上のフォルダーに抽出します。
1. macOS ターミナルのアプリを開き、`cd` コマンドを使用して前の手順で使用したフォルダーに切り替えます。
1. フォルダー内から、コマンド `./tf` を実行して、コマンド ライン クライアントが実行できることをテストします。Java またはその他の依存関係のインストールを求められる場合があります。

TEE-CLC がインストールされたら、コマンド `tf eula` を実行して、クライアント用のライセンス契約を表示して同意します。

最後に、お使いの TFS/Azure DevOps 環境による認証を行うために、サーバー上に個人用アクセス トークンを作成する必要があります。 詳しくは、「[Authenticating with personal access tokens (個人用アクセス トークンによる認証)](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/pats?view=azure-devops)」をご覧ください。 TFVC によって使用される個人用アクセス トークンを作成する場合は、トークンの構成時に必ずフル アクセスを指定してください。

### <a name="using-the-tee-clc-to-connect-to-your-repo"></a>TEE CLC を使用してリポジトリに接続する

ソース コードに接続するには、最初に、`tf workspace` コマンドを使用してワークスペースを作成する必要があります。 たとえば、次のコマンドでは、Azure DevOps Services にある "MyOrganization" という組織に接続します。 

```bash
export TF_AUTO_SAVE_CREDENTIALS=1
tf workspace -new MyWorkspace -collection:https://dev.azure.com/MyOrganization
```

`TF_AUTO_SAVE_CREDENTIALS` 環境設定は、入力を複数回求められることがないように、資格情報を保存するために使用されます。 ユーザー名の入力を求められたら、前のセクションで作成した個人用アクセス トークンを使用し、空白のパスワードを使用します。

ローカル フォルダーへのソース ファイルのマッピングを作成するには、`tf workfold` コマンドを使用します。 次の例では、"MyRepository" TFVC プロジェクトから "WebApp.Services" というフォルダーをマップし、local ~/Projects/ フォルダー (つまり、現在のユーザーのホーム フォルダーにある "Projects" フォルダー) にコピーされるように設定します。

```bash
tf workfold -map $/MyRepository/WebApp.Services -workspace:MyWorkspace ~/Projects/
```

最後に、次のコマンドを使用してサーバーからソース ファイルを取得し、ローカルにコピーします。

```bash
tf get
```

### <a name="committing-changes-using-the-tee-clc"></a>TEE CLC を使用して変更をコミットする

Visual Studio for Mac 内のファイルに変更を加えた後は、ターミナルに戻って編集内容をチェックインできます。 `tf add` コマンドは、チェックインされる保留中の変更一覧にファイルを追加するために使用され、`tf checkin` コマンドはサーバーへの実際のチェックインを実行します。 `checkin` コマンドには、コメントを追加したり、関連する作業項目を結び付けたりするためのパラメーターが含まれます。 次のコード スニペットでは、`WebApp.Services` フォルダーにあるすべてのファイルが、再帰的にチェックインに追加されます。 次に、コードはコメントと共にチェックインされ、ID "42" の作業項目と結び付けられます。

```bash
cd WebApp.Services
tf add * /recursive
tf checkin -comment:"Replaced 'Northwand' typos with the correct word Northwind" -associate:42
```

ここで説明したコマンドなどについて詳細を確認するには、ターミナルから次のコマンドを使用できます。

`tf help`

### <a name="see-also"></a>関連項目

- [Visual Studio を使用して TFVC でコードを開発および共有する (Windows)](/azure/devops/repos/tfvc/share-your-code-in-tfvc-vs)