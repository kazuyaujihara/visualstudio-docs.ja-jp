---
title: usings の生成
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 9fd34b40bdd1167eca7fa1dff8ab60bcc787b7c7
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57324757"
---
# <a name="generate-usings-in-visual-studio"></a>Visual Studio で usings を生成する

このコード生成は以下に適用されます。

- C#

**概要:****概要:** コピーして貼り付けたコードの必要なインポートまたは [using ステートメント](/dotnet/csharp/language-reference/keywords/using-statement)をすぐに追加できます。

**条件:** プロジェクトまたはその他のコード ソースでさまざまな場所からコードをコピーし、貼り付けることは一般的に行われます。 このクイック アクションによって、コピーして貼り付けたコードのインポートの足りない部分が分析され、追加するように求められます。

**理由:** 必要なインポートは自動的に追加されます。ユーザーは必要な `using` ステートメントを手動でコピーする必要がありません。

## <a name="generate-usings-refactoring"></a>usings リファクタリングの生成

1. 必要な `using` ステートメントを含めず、さまざまなファイルからコードをコピーし、貼り付けます。 エラーに付随してコード修正が行われ、足りない `using` ステートメントが追加されます。

    > [!NOTE] 
    > この提案は **[ツール]、[オプション]、[テキスト エディター]、[C#]、[詳細]、[ディレクティブを使用する]** でオンにする必要があります。

2. 行の任意の場所で **Ctrl**+**.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューが開きます。 

    ![usings の生成](media/generate-using-codefix.png)

3. **[using \<your reference\>]\(using <参照>)** を選択し、足りない参照を追加します。

    ![usings 生成の結果](media/generate-using-result.png)

## <a name="see-also"></a>関連項目

- [コード生成](../code-generation-in-visual-studio.md)
- [変更のプレビュー](../../ide/preview-changes.md)
- [.NET 開発者向けのヒント](../../ide/visual-studio-2017-for-dotnet-developers.md)