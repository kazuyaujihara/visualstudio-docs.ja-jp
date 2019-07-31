---
title: '[国際対応の設定] ([オプション] ダイアログ ボックス - [環境])'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Environment.InternationalSettings
- VS.ToolsOptionsPages.Environment.International_Settings
- VS.Environment.International Settings
helpviewer_keywords:
- International Settings dialog box
- languages, environment settings
- Options dialog box, international settings
- languages, specifying default
ms.assetid: e3a8815c-6995-4099-8e88-34f91fad55b2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 146aef659290df4302cc3bbb3d24a5bf6f1f01c8
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2019
ms.locfileid: "68605634"
---
# <a name="options-dialog-box-environment--international-settings"></a>[オプション] ダイアログ ボックス: [環境] \> [国際対応の設定]

コンピューターにインストールされている統合開発環境 (IDE) に複数の言語バージョンがある場合は、[国際対応の設定] ページで既定の言語を変更できます。 このダイアログ ボックスにアクセスするには、 **[ツール]** メニューの **[オプション]** を選択し、 **[環境]** フォルダーから **[国際対応の設定]** を選択します。

**Language**

インストールされている製品の言語バージョンで使用可能な言語の一覧が表示されます。 複数言語の製品または混合言語の製品で環境を共有する場合は、言語の選択が **[Microsoft Windows と同じ]** に変更されます。

> [!CAUTION]
> 複数の言語がインストールされているシステムでは、Visual C++ ビルド ツール (cl.exe、link.exe、nmake.exe、bscmake.exe、および関連ファイル) はこの設定による影響を受けません。 これらのツールでは、最後にインストールされた言語のバージョンを使用します。 Visual C++ ビルド ツールはサテライト DLL モデルを使用しないため、以前にインストールされた言語のビルド ツールは上書きされます。

### <a name="see-also"></a>関連項目

- [言語パックのインストール](../../install/install-visual-studio.md#step-6---install-language-packs-optional)