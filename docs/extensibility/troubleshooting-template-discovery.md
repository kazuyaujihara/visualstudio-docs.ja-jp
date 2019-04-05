---
title: Visual Studio でテンプレート検出のトラブルシューティング |Microsoft Docs
ms.date: 01/02/2018
ms.topic: conceptual
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a1ea74d3c5f3fed961a956e9a55a4930d009d530
ms.sourcegitcommit: d4bea2867a4f0c3b044fd334a54407c0fe87f9e8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58790226"
---
# <a name="troubleshooting-template-installation"></a>テンプレートのインストールのトラブルシューティング

プロジェクトまたは項目テンプレートのデプロイ時に問題が発生した場合は、診断ログを有効にできます。

::: moniker range="vs-2017"

1. Pkgdef ファイルを作成、 *Common7\IDE\CommonExtensions*フォルダーに、インストールします。 たとえば、 *C:\Program Files (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\EnablePkgDefLogging.pkgdef*します。

::: moniker-end

::: moniker range=">=vs-2019"

1. Pkgdef ファイルを作成、 *Common7\IDE\CommonExtensions*フォルダーに、インストールします。 たとえば、 *C:\Program Files (x86) \Microsoft Visual Studio\2019\Enterprise\Common7\IDE\CommonExtensions\EnablePkgDefLogging.pkgdef*します。

::: moniker-end

2. Pkgdef ファイルには、次を追加します。

    ```
    [$RootKey$\VsTemplate]
    "EnableTemplateDiscoveryLog"=dword:00000001
    ```

3. 開く、[開発者コマンド プロンプト](/dotnet/framework/tools/developer-command-prompt-for-vs)、インストールと実行の`devenv /updateConfiguration`します。

::: moniker range="vs-2017"

4. Visual Studio を開き、両方のテンプレートのツリーを初期化するために新しいプロジェクトと新しい項目 ダイアログ ボックスを起動します。

   テンプレートは、ログに表示されている **%LOCALAPPDATA%\Microsoft\VisualStudio\15.0_[instanceid]\VsTemplateDiagnosticsList.csv** (インスタンス id は、Visual Studio のインスタンスのインストール ID に対応)。 各テンプレート ツリーの初期化では、このログにエントリを追加します。

::: moniker-end

::: moniker range=">=vs-2019"

4. Visual Studio と起動を開く、**新しいプロジェクトを作成**と**新しい項目の**両方のテンプレートのツリーを初期化するためにダイアログ ボックス。

   テンプレートは、ログに表示されている **%LOCALAPPDATA%\Microsoft\VisualStudio\16.0_[instanceid]\VsTemplateDiagnosticsList.csv** (インスタンス id は、Visual Studio のインスタンスのインストール ID に対応)。 各テンプレート ツリーの初期化では、このログにエントリを追加します。

::: moniker-end

ログ ファイルには、次の列が含まれています。

- **FullPathToTemplate**、次の値を持ちます。

    - マニフェスト ベースの展開 1

    - ディスク ベースの展開の場合は 0

- **TemplateFileName**

- その他のテンプレートのプロパティ

> [!NOTE]
> ログ記録を無効にするか、pkgdef ファイルを削除またはの値を変更`EnableTemplateDiscoveryLog`に`dword:00000000`、し、実行`devenv /updateConfiguration`もう一度です。

## <a name="see-also"></a>関連項目

- [カスタム プロジェクトと項目テンプレートの作成](creating-custom-project-and-item-templates.md)