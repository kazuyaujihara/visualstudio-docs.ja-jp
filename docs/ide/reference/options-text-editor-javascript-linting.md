---
title: '[オプション]、[テキスト エディター]、[JavaScript]、[Lint 処理]'
ms.date: 1/15/2019
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Linting.General
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Linting
- VS.ToolsOptionsPages.Text_Editor.TypeScript.Linting.General
- VS.ToolsOptionsPages.Text_Editor.TypeScript.Linting
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 74cd522da1d29ce7f9a58737fc44ecec0909ed1f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62778340"
---
# <a name="options-text-editor-javascript-linting"></a>[オプション]、[テキスト エディター]、[JavaScript]、[Lint 処理]

**[オプション]** ダイアログ ボックスの **[Lint 処理]** ページを使用して、コード エディターでコードを分析するためのプションを設定します。 このページにアクセスするには、メニュー バーで **[ツール]** > **[オプション]** を選択し、**[テキスト エディター]** > **[JavaScript]** > **[Lint 処理]** を展開します。

## <a name="eslint-settings"></a>ESLint 処理設定

これらのオプションを使用して、JavaScript コードの静的解析を有効にし、どのファイルを解析するかを選択できます。 ESLint の詳細については、[ESLint.org](https://eslint.org/) を参照してください。

### <a name="uielement-list"></a>UIElement の一覧

|オプション|説明|
|------------|-----------------|
|**ESLint を有効にする**|このオプションを選択すると、コード エディターでコードの静的解析を実行できます。|
|**プロジェクトに含まれるすべてのファイルを Lint 処理する (閉じているファイルも含む)**|このオプションを選択すると、診断のレポート対象が開いているファイルに限定されていない限り、閉じているファイルも解析されます。|

## <a name="global-eslint-config-options"></a>ESLint のグローバル構成オプション

このオプションを使用して、グローバルな ESLint 構成ファイルの場所をコピーできます。 場所を変更している場合は、既定の場所にファイルをリセットできます。

## <a name="see-also"></a>関連項目

- [[全般]、[環境]、[オプション] ダイアログ ボックス](../../ide/reference/general-environment-options-dialog-box.md)