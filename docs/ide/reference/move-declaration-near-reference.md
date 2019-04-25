---
title: 参照の近くに変数宣言を移動する
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: e23c5c8d6ea0895f9e5a78e726bb7a7cede071bb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62540597"
---
# <a name="move-declaration-near-reference-refactoring"></a>参照の近くへの宣言の移動リファクタリング

このリファクタリングは以下に適用されます。

- C#

**概要:** 変数宣言を使用箇所の近くに移動できます。

**条件:** より狭いスコープに保持できる変数宣言があるとき。

**理由:** そのままにしておくこともできますが、読みやすさの問題または情報の隠蔽を招く可能性があります。 これは、読みやすさを向上させるためにリファクタリングするチャンスです。

## <a name="how-to"></a>方法

1. 変数宣言にカーソルを置きます。

1. 次に、以下のいずれかを実行します。

   - **キーボード**
      - 行の任意の場所で **Ctrl**+**.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーし、[プレビュー] ウィンドウ ポップアップから **[宣言を参照の近くに移動]** を選択します。
   - **マウス**
      - コードを右クリックして **[クイック アクションとリファクタリング]** メニューを選択し、[プレビュー] ウィンドウ ポップアップから **[宣言を参照の近くに移動]** を選択します。

1. 変更を確認したら、**Enter** キーを押すか、メニューの [修正] をクリックすると、変更がコミットされます。

例:

```csharp
// Before
int x;
if (condition)
{
    x = 1;
    Console.WriteLine(x);
}

// Move declaration near reference

// After
if (condition)
{
    int x = 1;
    Console.WriteLine(x);
}
```

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)
- [変更のプレビュー](../../ide/preview-changes.md)