---
title: 抽象クラスの実装
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 1e5e1d05e0142a0185909ff590ff507fb53c7dc0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62823183"
---
# <a name="implement-an-abstract-class-in-visual-studio"></a>Visual Studio で抽象クラスを実装する

このコード生成は以下に適用されます。

- C#

- Visual Basic

**機能:** 抽象クラスを実装するために必要なコードをすぐに生成できます。

**条件:** 抽象クラスから継承したいとき。

**理由:** すべての抽象メンバーは 1 つずつ手動で実装できますが、この機能ではすべてのメソッド シグネチャが自動的に生成されます。

## <a name="how-to"></a>方法

1. 抽象クラスを継承しているが、必要なすべてのメンバーを実装していないことを示す赤い波線がある行に、カーソルを置きます。

   - C#: 

       ![強調表示された C# のコード](media/abstract-highlight-cs.png)

   - Visual Basic: 

       ![強調表示された VB のコード](media/abstract-highlight-vb.png)

2. 次に、以下のいずれかを実行します。

   - **キーボード**
      - 行の任意の場所で **Ctrl**+**.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。
   - **マウス**
      - 右クリックして **[クイック アクションとリファクタリング]** メニューを選択します。
      - 赤い波線をポイントし、表示された ![エラー電球](media/error-bulb.png) アイコンをクリックします。
      - テキスト カーソルが既に赤い波線の行にある場合は、左余白に表示されている ![エラー電球](media/error-bulb.png) アイコンをクリックします。

   ![クラス実装のプレビュー](media/abstract-preview-cs.png)

3. ドロップダウン メニューから **[抽象クラスの実装]** を選びます。

   > [!TIP]
   > - プレビュー ウィンドウの下部にある **[変更のプレビュー]** リンクを使うと、選択する前に、行われる[すべての変更を確認する](../../ide/preview-changes.md)ことができます。
   > - 抽象クラスから継承する複数のクラスにまたがる適切なメソッド シグネチャを作成するには、プレビュー ウィンドウの下部にある **[ドキュメント]**、**[プロジェクト]**、**[ソリューション]** の各リンクを使います。

   抽象メソッドのシグネチャが作成され、実装する準備が整います。

   - C#: 

       ![クラス実装の結果 C#](media/abstract-result-cs.png)

   - Visual Basic: 

       ![クラス実装の結果 VB](media/abstract-result-vb.png)

## <a name="see-also"></a>関連項目

- [コード生成](../code-generation-in-visual-studio.md)
- [変更のプレビュー](../../ide/preview-changes.md)