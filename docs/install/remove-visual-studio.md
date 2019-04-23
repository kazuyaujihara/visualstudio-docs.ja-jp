---
title: Visual Studio の削除
titleSuffix: ''
description: コンピューターから Visual Studio を完全に削除する詳細な手順を説明します。
ms.date: 03/30/2019
ms.custom: seodec18
ms.topic: conceptual
f1_keywords:
- uninstall
- uninstall Visual Studio
- remove
- remove Visual Studio
- cleanup
- cleanup Visual Studio
- clean up
- clean up Visual Studio
ms.assetid: 9c81a777-9c95-4934-b517-c60c6dc78799
author: heaths
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 779771c51299239814f7ddd6a9cdbfbed017ac72
ms.sourcegitcommit: d4bea2867a4f0c3b044fd334a54407c0fe87f9e8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58790122"
---
# <a name="remove-visual-studio"></a>Visual Studio の削除

致命的なエラーが発生して Visual Studio の修復またはアンインストールができない場合は、`InstallCleanup.exe` ツールを実行して Visual Studio 2017 または Visual Studio 2019 のすべてのインストール済みインスタンスのインストール ファイルと製品情報を削除することができます。 このツールの実行は、修復またはアンインストールに失敗した場合の最終手段としてのみ行ってください。その他の Visual Studio のインストールやその他の製品の機能がアンインストールされ、後で修復が必要になる場合もあります。

次の手順では、以下の動作のコマンドライン スイッチでツールを実行することができます。

| 切り替え | 動作 |
| ------ | -------- |
| `-i`   | その他のスイッチが渡されていない場合、このスイッチが既定で、メインのインストール ディレクトリと製品情報のみが削除されます。 `InstallCleanup.exe` ツールを実行した後に同じバージョンを再インストールする予定がある場合は、この動作が適しています。 |
| `-f`   | このスイッチを指定すると、メインのインストール ディレクトリ、製品情報、そして他の Visual Studio のインストールまたは他の製品と共有できるインストール ディレクトリ外にインストールされているその他の多くの機能が削除されます。 この動作は、後で再インストールせずに Visual Studio を削除する場合に適しています。 |

1. Visual Studio インストーラーを閉じます。
2. 管理者のコマンド プロンプトを開きます。 管理者のコマンド プロンプトを開くには、以下の手順に従います。
   * [検索するテキストをここに入力] ボックスに、「**cmd**」と入力します。
   * **[Command Prompt]** を右クリックし、**[管理者として実行]** をクリックします。
3. `InstallCleanup.exe` ユーティリティの完全なパスを入力して、必要なコマンドライン スイッチを渡します。 既定では、ユーティリティのパスは次のようになります。
   ```
   C:\Program Files (x86)\Microsoft Visual Studio\Installer\resources\app\layout\InstallCleanup.exe
   ```

通常は `%ProgramFiles(x86)%\Microsoft Visual Studio` にある `InstallCleanup.exe` が Visual Studio インストーラー ディレクトリの下に見つからない場合は、[Visual Studio のインストール](install-visual-studio.md)の手順に従い、ワークロード選択画面が表示されたら、ウィンドウを閉じて前の手順をもう一度実行します。

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>関連項目

* [Visual Studio のインストール](install-visual-studio.md)
* [Visual Studio の更新](update-visual-studio.md)
* [Visual Studio の変更](modify-visual-studio.md)
* [Visual Studio のアンインストール](uninstall-visual-studio.md)
