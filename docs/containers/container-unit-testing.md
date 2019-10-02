---
title: コンテナー化されたアプリの単体テスト
author: ghogen
description: Visual Studio 内で Docker プロジェクト用のすべてのビルドを使用して単体テストを実行する
ms.author: ghogen
ms.date: 06/17/2019
ms.technology: vs-azure
ms.topic: conceptual
ms.openlocfilehash: ec5aea44362cf82f6745671cc0706f80e01a60ad
ms.sourcegitcommit: 0cd282a7584b9bfd4df7882f8fdf3ad8a270e219
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "71125969"
---
# <a name="how-to-run-unit-tests-for-a-containerized-app"></a>方法: コンテナー化されたアプリの単体テストを実行する

Dockerfile を変更することで、コンテナー化されたプロジェクトのすべてのビルドを使用して、単体テストを実行することができます。

## <a name="prerequisites"></a>必須コンポーネント

- [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) をインストールする
- [dotnet test](/dotnet/core/tools/dotnet-test) を使用して実行されるように設定された単体テスト
- [[コンテナー] ウィンドウ拡張機能](https://aka.ms/vscontainerspreview)をインストールする

## <a name="add-unit-tests-to-the-dockerfile"></a>Dockerfile に単体テストを追加する

Visual Studio では、Dockerfile を変更する前に、特別なパフォーマンス最適化がいくつか行われます。 **デバッグ**構成をビルドするとき、Visual Studio では、ローカル コンピューター上でプロジェクトがビルドされ、結果がコンテナーにコピーされます。 そのため、Dockerfile で指定されているとおり、マルチステージ Dockerfile の最初のステージのみが実行されます。 詳細については、[Visual Studio でのコンテナー ツールのビルド プロセス](container-build.md)に関するページを参照してください。

マルチステージ Dockerfile に単体テストを追加するには、`build` ステージと `publish` ステージの間で、`unit-test` ステージを Dockerfile に追加します。

```
FROM build AS unit-test
RUN dotnet unit-test --logger:trx
```

Visual Studio では、**デバッグ**構成で最初のステージのみが実行されるため、`unit-test` ステージは **リリース**構成でのみ実行されます。 最終ステージは、`unit-test` ステージではなく、`base` ステージからビルドされるため、**リリース**構成であっても、ログの結果は最終イメージに含まれません。 テストを実行し、ログを表示できるイメージを生成するには、次のコマンドを使用します。

```cmd
docker build --target:unit-test
```

## <a name="next-steps"></a>次の手順

次に、[[コンテナー] ウィンドウ](view-and-diagnose-containers.md) (拡張機能がインストールされている場合) を使用して、テスト ログを表示します。  

テスト ログを表示するには、**Ctrl** + **Q** キーを使用して、**コンテナー**を検索し、 **[コンテナー]** ウィンドウを開きます。 **[コンテナー]** ウィンドウで、自分のコンテナーを検索し、 **[ファイル]** タブを開きます。コンテナーのファイルシステムでテスト結果 (.trx) ファイルを探して、そのファイルを開くと、Visual Studio に結果が表示されます。

