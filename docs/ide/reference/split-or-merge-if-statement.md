---
title: if ステートメントの分割または結合
ms.date: 06/12/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 405ccd4bc0197ce06aa14982a16dc02f6d13a537
ms.sourcegitcommit: d4920babfc3d24a3fe1d4bf446ed3fe73b344467
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2019
ms.locfileid: "67160738"
---
# <a name="split-or-merge-if-statements"></a>if ステートメントの分割または結合

このリファクタリングは以下に適用されます。

- C#

**概要:** **概要:** [if](/dotnet/csharp/language-reference/keywords/if-else) ステートメントを分割または結合します。

**条件:** `&&` または `||` 演算子が使われている `if` ステートメントを、入れ子になった `if` ステートメントに分割します。または、`if` ステートメントを外側の `if` ステートメントと結合します。

**理由:** スタイルの好みの問題です。  

## <a name="how-to"></a>方法

`if` ステートメントを分割する場合:

1. `&&` または `||` 演算子による `if` ステートメント内にカーソルを置きます。

2. 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。

    ![if ステートメントを分割する](../media/split-if-statement.png)

3. **[Split into nested if statements]\(入れ子になった if ステートメントに分割する\)** を選択します。

    ![完了した if ステートメントの分割](../media/split-if-statement-complete.png)

内側の `if` ステートメントと外側の `if` ステートメントを結合する場合: 

1. 内側の `if` キーワードにカーソルを置きます。

2. 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。

    ![if ステートメントを結合する](../media/merge-if-statement.png)

3. **[Merge with outer if statement]\(外側の if ステートメントと結合する\)** を選択します。

    ![完了した if ステートメントの結合](../media/merge-if-statement-complete.png)

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)