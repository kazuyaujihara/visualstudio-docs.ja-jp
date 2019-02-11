---
title: レイヤー モデル拡張機能の配置
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, deploying extensions
- layer models, deploying extensions
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 594f4118f8c6876857b862d6423180403f4f96c6
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55915622"
---
# <a name="deploy-a-layer-model-extension"></a>レイヤー モデル拡張機能の配置

Visual Studio の他のユーザーは、Visual Studio を使って作成されたレイヤー モデリング拡張機能をインストールできます。

## <a name="install-your-extension"></a>拡張機能をインストールします。

拡張機能をコンパイルすると VSIX ファイルが作成され、これを他のコンピューターにインストールできます。 また、このファイルを開発用コンピューターにインストールし、Visual Studio のメイン インスタンスで拡張機能を使用できるようにすることもできます。

### <a name="to-install-the-extension"></a>拡張機能をインストールするには

1. 含むプロジェクトで**source.vsix.manifest**、オープン、 *bin*ファイル エクスプ ローラーでディレクトリ。

2. コピー、  **\*.vsix**ファイルを拡張機能をインストールするコンピューターにします。

3. ターゲット コンピューターの Windows エクスプローラーで *.vsix をダブルクリックします。

    VSIX インストーラーが起動します。

### <a name="to-uninstall-the-extension"></a>拡張機能をアンインストールするには

1.  Visual Studio での**ツール** メニューのをクリックして**拡張機能と更新**します。

2.  拡張機能の名前をクリックし、クリックして**アンインストール**します。

## <a name="install-an-extension-on-team-foundation-server"></a>Team Foundation Server の拡張機能をインストールします。

Team Foundation Server のサーバーに通常 Visual Studio をインストールするがないと、これをダブルクリックして、VSIX をインストールすることはできません。 拡張機能を手動でインストールする必要があります。

### <a name="to-install-your-layer-extension-on-a-team-foundation-server-server"></a>Team Foundation Server サーバーで、レイヤーの拡張機能をインストールするには

1.  コピーします。*vsix*開発用コンピューターからファイルを Team Foundation Server (TFS) のコンピューターにします。

     VSIX ファイルを次のいずれかの場所に置きます。

    -   すべてのユーザーおよびサービスを対象にインストールする場合:

         %ProgramFiles%\Microsoft Visual Studio [バージョン]\Common7\IDE\Extensions\Microsoft

    -   ビルドを実行するネットワーク サービスに対してのみインストールするのには。

         %WinDir%\ServiceProfiles\NetworkService\AppData\Local\Microsoft\VisualStudio\\[version]\Extensions\Microsoft

    -   特定のユーザーとして対話型モードで実行するビルドを構成した場合は、そのユーザーに対してのみインストールできます。

         %LocalAppData%\Microsoft\VisualStudio\\[version]\Extensions\Microsoft

2.  各 VSIX ファイルを同じ場所のフォルダーに展開します。

    1.  ファイル名拡張子が変更 **.vsix**に **.zip**します。

    2.  .zip ファイルの内容をフォルダーに抽出します。

    3.  .zip ファイルを削除します。

3.  TFS を再起動します。
