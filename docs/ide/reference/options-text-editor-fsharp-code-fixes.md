---
title: '[オプション]、[テキスト エディター]、[F#]、[コード修正]'
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.F%2523.Code_Fixes
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: a73991702455fab54baf868499634e1a4f5bbf48
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68870747"
---
# <a name="options-text-editor--f--code-fixes"></a>オプション:[テキスト エディター] > [F#] > [コード修正]

[コード修正] オプション ページを使用して、コード エラーを識別し、ソリューションを提供するために役立つ設定を指定します。 このオプション ページにアクセスするには、 **[ツール]**  >  **[オプション]** を選び、さらに **[テキスト エディター]**  >  **[F#]**  >  **[コード修正]** の順に選びます。

## <a name="code-fixes"></a>コード修正

- **名前を単純化する (不要な修飾子を削除する)**

  このチェック ボックスをオンすると、完全修飾名の修飾が不要な場合 (頻繁に使用される名前空間のメンバーなど) に、名前が単純化されます。

- **Open ステートメントを常に最上位レベルに配置する**

  このチェック ボックスをオンにしているときに、コード内に `open` ステートメントを入力すると、それが最上位レベルで配置されます。

- **未使用の Open ステートメントを削除する**

  このチェック ボックスをオンにすると、使用されていない `open` ステートメントがドキュメントで分析され、未使用の `open` ステートメントをすべて削除するためのアクションを含む[クイック アクション](../quick-actions.md)の電球が表示されます。

- **未使用の値を解析して修正を提案する**

  このチェック ボックスをオンにすると、コード内の使用されていない値が認識されます。 その後、未使用の値をポイントすると、値を使用できる方法が推奨されます。

## <a name="see-also"></a>関連項目

- [[全般]、[環境]、[オプション] ダイアログ ボックス](../../ide/reference/general-environment-options-dialog-box.md)
- [CodeLens によるコード変更とその他の履歴の検索](../../ide/find-code-changes-and-other-history-with-codelens.md)
