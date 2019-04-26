---
title: XAML デザイナーでのオブジェクトのアニメーション化
ms.date: 04/11/2018
ms.topic: conceptual
ms.assetid: fb88fa26-e835-47f5-9771-2f279441c83c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: a5bd9c24351201d066f9055554468939df02b33e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62927032"
---
# <a name="animate-objects-in-xaml-designer"></a>XAML デザイナーでのオブジェクトのアニメーション化

オブジェクトを動かす短いアニメーションを作成したり、フェードインとフェードアウトを行うことができます。

最初に、 *ストーリー ボード*を作成します。 ストーリー ボードには、1 つ以上の *タイムライン*があります。 タイムライン上で *キーフレーム* を設定してプロパティの変更をマークします。 次に、アニメーションの実行時に、Blend は、指定した期間全体でプロパティの変更を補間します。 結果として、移行がスムーズになります。 オブジェクトに属する任意のプロパティをアニメーション化できます。非視覚プロパティでも同様です。

次の図は、「 **MoveUp**」という名前のストーリーボードを示しています。 タイムラインには、四角形の X と Y 位置をマークするキーフレームが含まれています。 このアニメーションを実行すると、四角形はある位置から別の位置にスムーズに移動します。

![XAML デザイナーの MoveUp ストーリーボード](../designers/media/982f031a-74a3-414a-abc2-a0f41a741075.png)

## <a name="see-also"></a>関連項目

- [Blend for Visual Studio を使用した UI の作成](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)