---
title: コードのスタイル設定
ms.date: 03/12/2019
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.workload:
- multiple
ms.openlocfilehash: a7a478e8d3575e70a11ec776d59337ae93e7a677
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "57873361"
---
# <a name="code-style-preferences"></a>コードのスタイル設定

C# プロジェクトおよび Visual Basic プロジェクトに対してコードのスタイル設定を設定するには、**[ツール]** メニューから **[オプション]** ダイアログ ボックスを開きます。 **[オプション]** ダイアログ ボックスで、**[テキスト エディター]** > **[C#]** または **[Basic]** > **[コード スタイル]** > **[全般]** の順に選択します。 選択すると、リスト内の各項目について優先順位のプレビューが表示されます。

![コード スタイルのオプション](media/code-style-quick-actions-dialog.png)

このウィンドウで設定したオプションは、Visual Studio のパーソナル化アカウントに適用され、特定のプロジェクトまたはコードベースには関連付けられません。 さらに、継続的インテグレーション (CI) のビルドなど、ビルド時には適用されません。 コード スタイルのユーザー設定をプロジェクトに関連付けて、ビルド時にスタイルを適用する場合は、[.editorconfig ファイル](#editorconfig-files)でユーザー設定を指定します。

> [!NOTE]
> このトピックは、Windows 上の Visual Studio に適用されます。 Visual Studio for Mac については、[Visual Studio for Mac でのエディターの動作](/visualstudio/mac/editor-behavior)に関するページを参照してください。

## <a name="preference-and-severity"></a>優先順位と重大度

各行のドロップダウン リストを使って、項目ごとに **[優先順位]** と **[重大度レベル]** の値を設定できます。 重大度は、**なし**、**提案**、**警告**、または **エラー**に設定できます。 コード スタイルの[クイック アクション](../ide/quick-actions.md)を有効にする場合、**[重大度レベル]** の設定は**なし**以外に設定してください。 **クイック アクション**の電球 ![電球](media/light-bulb-dropdown.png)、エラー電球 ![エラー電球](media/error-bulb.png)、ねじ回し ![ねじ回し](media/screwdriver.png) アイコンは、優先されていないスタイルが使用されていて、**[クイック アクション]** 一覧のオプションを選ぶと優先されるスタイルにコードが自動的に再作成されると表示されます。

## <a name="editorconfig-files"></a>EditorConfig ファイル

.NET に対するコード スタイルの設定は、[EditorConfig](../ide/editorconfig-code-style-settings-reference.md) ファイルをプロジェクトに追加することによって指定することもできます。 これらのファイルは、Visual Studio のパーソナル化アカウントではなく、コードベースに関連付けられます。 EditorConfig ファイル内の設定が、**[オプション]** ダイアログ ボックスで選択したオプションよりも優先されます。 リポジトリまたはプロジェクトに対するすべての共同作成者にコーディング スタイルを適用する場合は、EditorConfig ファイルを使用します。

## <a name="format-document-command"></a>[ドキュメントのフォーマット] コマンド

using の削除と並べ替え、コード スタイルの基本設定の適用など、ファイルでの追加コードのクリーンアップを行うように **[ドキュメントのフォーマット]** コマンド (**[編集]** > **[詳細設定]** > **[ドキュメントのフォーマット]**) を構成することができます。 [[書式設定] オプション ページ](reference/options-text-editor-csharp-formatting.md#format-document-settings)で、**ドキュメントのフォーマット**で適用する設定を定義することができます。

コードのクリーンアップでは、*.editorconfig* ファイルで構成した設定が優先されます。そのルールまたはファイルがない場合は、**[ツール]** > **[オプション]** > **[テキスト エディター]** > **[C#]** > **[コード スタイル]** または **[書式設定]** の設定が優先されます。

Visual Studio で初めて **[ドキュメントのフォーマット]** コマンドをトリガーするときに、黄色の情報バーが表示され、コードのクリーンアップ設定を構成するように求められます。

> [!TIP]
> 重大度が**なし**で構成されているルールは、コードのクリーンアップには関係しませんが、**[クイック アクションとリファクタリング]** メニューを使用して個別に適用できます。

## <a name="see-also"></a>関連項目

- [クイック アクション](../ide/quick-actions.md)
- [EditorConfig の .NET コーディング規則の設定](../ide/editorconfig-code-style-settings-reference.md)
- [エディターの動作 (Visual Studio for Mac)](/visualstudio/mac/editor-behavior)