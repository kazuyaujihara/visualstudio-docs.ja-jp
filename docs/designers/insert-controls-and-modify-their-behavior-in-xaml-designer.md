---
title: XAML デザイナー でコントロールを挿入し、そのビヘイビアーを変更する
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: a80fff74-bf01-41c9-ab85-ada7a873c3a9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: edb657779e8c404032d71061132816a2a30c83c9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62893455"
---
# <a name="insert-controls-and-modify-their-behavior-in-xaml-designer"></a>XAML デザイナー でコントロールを挿入し、そのビヘイビアーを変更する

コントロールは、ユーザーとアプリとの対話を可能にします。 コントロールを使用すると、情報を収集できるとともに、オブジェクトのアニメーション化や、データ ソースのクエリなどのアクションを実行できます。

## <a name="add-controls-to-the-artboard"></a>アートボードにコントロールを追加する

コントロールは、 **[アセット]** パネルから **アートボード**にドラッグし、 **[プロパティ]** ウィンドウで修正できます。

![Blend の [アセット] タブ コントロール](../designers/media/blend_assetsflipview_xaml.png)

### <a name="make-a-control-out-of-an-image-shape-or-path"></a>イメージ、図形、またはパスからコントロールを作成する

あらゆるオブジェクトをコントロールにすることができます。

![Blend の [コントロールの作成] ダイアログ ボックス](../designers/media/blend_makeintocontrol_xaml.png)

たとえば、ページの中央にテレビの画像があるところを想像してください。 テレビのボタンのような小さいイメージからコントロールを作成できます。 次に、このボタンをクリックしてチャンネルを変更します。

これが可能なのは、ボタンがコントロールになったためです。 コントロールを使用すると;、ユーザーの操作に応答することができます。この場合は、ユーザーがボタンをクリックしたときです。

コントロールを作成するには、オブジェクトを選択します。 **[ツール]** メニューで **[コントロールの作成]** をクリックします。

## <a name="make-controls-do-things"></a>コントロールの操作を行う

コントロールは、ユーザーが操作したときにアクションを実行します。 たとえば、アニメーションの開始、データ ソースの更新、またはビデオの再生を行えます。

*トリガー*、 *ビヘイビアー*、 *イベント* を使用して、コントロールの操作を実行します。

### <a name="triggers"></a>トリガー

*トリガー* は、プロパティを変更したり、イベントまたは別のプロパティの変更に応じてタスクを実行できます。 たとえば、ユーザーがボタンの上にマウスのポインタを置くとボタンの色が変化するなどです。

![[トリガー] パネル](../designers/media/custom_button_blend_propertytriggerinfo.png)

### <a name="behaviors"></a>ビヘイビアー

*ビヘイビアー* は再利用可能なコードのパッケージです。 ビヘイビアーは、プロパティの変更より少し多くのことができます。 データ サービスのクエリなどのアクションを実行できます。 Blend には小さな動作のコレクションが付属していますが、さらに追加することができます。 ビヘイビアーをアートボード内のオブジェクトにドラッグしてから、プロパティを設定してビヘイビアーをカスタマイズします。

![[プロパティ] パネルの FluidMoveBehavior](../designers/media/b4_fluidmovebehaviorproperties_sample.png)

**ビデオを見る:**![[再生] アイコン](../designers/media/bldadminconsoleinitialconfigicon.PNG) [Blend のヒント:ビヘイビアーの使用の概要パート 1](http://www.bing.com/videos/search?q=Expression%20blend%20behaviors&qs=n&form=QBVR&pq=expression%20blend%20behavior&sc=4-25&sp=-1&sk=#view=detail&mid=CF0DD797ED84DE740904CF0DD797ED84DE740904)。

### <a name="events"></a>イベント

柔軟性を最大にするため、 *イベント*を処理します。 いくつかのコードを記述する必要があります。