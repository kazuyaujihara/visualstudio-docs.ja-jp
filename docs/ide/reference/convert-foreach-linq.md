---
title: Foreach ループを LINQ に変換する
ms.date: 02/20/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: eadad8fdbec990607450b374a32758547194f734
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58160275"
---
# <a name="convert-foreach-loop-to-linq"></a>Foreach ループを LINQ に変換する

このリファクタリングは以下に適用されます。

- C#

**概要:** IEnumerables を使用する Foreach ループを LINQ クエリまたは LINQ 呼び出し形式 (別名 LINQ メソッド) に簡単に変換できます。

**条件:** LINQ クエリとして読み取る IEnumerable を使用する Foreach ループがあるとき。

**理由:** Foreach ループではなく LINQ 構文の使用を好むユーザーもいます。 [LINQ](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq) により、クエリは C# での高度な言語構成要素になります。 LINQ では、ファイルのコードの量が減り、読み取りが簡単になります。また、さまざまなデータ ソースで同様のクエリ式パターンを指定できます。

> [!NOTE]
> LINQ 構文は一般的に、Foreach ループに比べてパフォーマンスが低くなります。 LINQ でコードの読みやすさを改善するときはパフォーマンスが低下する可能性があることを考慮することをお勧めします。

## <a name="convert-foreach-loop-to-linq-refactoring"></a>Foreach ループを LINQ リファクタリングに変換する

1. `foreach` キーワードにカーソルを置きます。

    ![IEnumerable を使用する Foreach](media/convert-foreach-to-LINQ.png)

2. 行の任意の場所で **Ctrl**+**.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。

   ![LINQ に変換メニュー](media/convert-foreach-to-LINQ-codefix.png)

3. **[Convert to LINQ]\(LINQ に変換\)** または **[Convert to LINQ (call form)]\(LINQ に変換 (呼び出し形式)\)** を選択する

   ![LINQ クエリの結果](media/convert-foreach-to-LINQ-result.png)
   
   ![LINQ 呼び出し形式の結果](media/convert-foreach-to-LINQ-callform-result.png)

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)
- [変更のプレビュー](../../ide/preview-changes.md)
- [.NET 開発者向けのヒント](../../ide/visual-studio-2017-for-dotnet-developers.md)