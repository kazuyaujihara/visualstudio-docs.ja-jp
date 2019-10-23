---
title: 一時変数をその値と置き換える
ms.date: 01/26/2018
ms.topic: reference
author: jillre
ms.author: jillfra
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 8b758407dc5500630157050c10f881a6515e1216
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661013"
---
# <a name="inline-a-temporary-variable-refactoring"></a>一時変数のインライン化リファクタリング

このリファクタリングは以下に適用されます。

- C#

- Visual Basic

**概要:** 一時変数を削除し、代わりにその値に置換できます。

**条件:** 一時変数の使用により、コードの理解が困難になったとき。

**理由:** 一時変数を削除すると、コードが読みやすくなることがあるため。

## <a name="how-to"></a>方法

1. インライン化する一時変数を強調表示するか、一時変数の内側にテキスト カーソルを置きます。

   - C#:

       ![強調表示されたコード - C#](media/inline-highlight-cs.png)

   - Visual Basic:

       ![強調表示されたコード - Visual Basic](media/inline-highlight-vb.png)

2. 次に、以下のいずれかを実行します。

   - **キーボード**
      - 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。
   - **マウス**
      - コードを右クリックして **[クイック アクションとリファクタリング]** メニューを選択します。

3. [プレビュー] ウィンドウ ポップアップから **[インラインの一時変数]** を選択します。

   変数が削除されて、その使用箇所が変数の値に置き換えられます。

   - C#:

      ![インラインの結果 - C#](media/inline-result-cs.png)

   - Visual Basic:

      ![インラインの結果 - Visual Basic](media/inline-result-vb.png)

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)