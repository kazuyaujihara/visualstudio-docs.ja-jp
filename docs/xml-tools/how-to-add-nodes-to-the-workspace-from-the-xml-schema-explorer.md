---
title: XML スキーマエクスプローラーからワークスペースにノードを追加する
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 3b5a5749-9693-4b29-b0c2-8e07e0e55514
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 77e1890df09443e133f9e528905b76374f6070bc
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72646040"
---
# <a name="how-to-add-nodes-to-the-workspace-from-the-xml-schema-explorer"></a>方法: XML スキーマエクスプローラーからワークスペースにノードを追加する

このトピックでは、 **Xml スキーマエクスプローラー**から[xml スキーマデザイナーワークスペース](../xml-tools/xml-schema-designer-workspace.md)にノードを追加する方法について説明します。 これを実現するには、 **Xml スキーマエクスプローラー**から XSD デザイナービューにノードをドラッグアンドドロップするか、 **xml スキーマエクスプローラーの**コンテキストメニューを使用します。 また、 **XML スキーマエクスプローラー**によって実行される検索の結果として強調表示されているノードを追加することもできます。 詳細については、「[方法: スキーマセットの検索結果ノードをワークスペースに追加する](../xml-tools/how-to-add-schema-set-search-result-nodes-to-the-workspace.md)」を参照してください。

> [!NOTE]
> [XML スキーマデザイナーのワークスペース](../xml-tools/xml-schema-designer-workspace.md)に追加できるのは、グローバルノードだけです。

## <a name="to-add-nodes-through-the-xml-explorer-context-menu"></a>XML エクスプローラーのショートカットメニューを使用してノードを追加するには

1. [「方法: XSD スキーマファイルを作成および編集する](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)」の手順に従います。

2. XSD エクスプローラーで、[`PurchaseOrderType`] ノードを右クリックします。 **[グラフビューで表示]** を選択します。

     `purchaseOrderType` ノードがグラフ ビューのデザイン サーフェイスに表示されます。

## <a name="to-drag-and-drop-a-node-on-to-a-view"></a>ビューにノードをドラッグ アンド ドロップするには

1. グラフビューの [`PurchaseOrderType`] ノードを右クリックします。 **[XML スキーマエクスプローラーで表示]** を選択します。

     **XML スキーマエクスプローラー**で、ノードが強調表示されます。

2. **XML スキーマエクスプローラー**で [`PurchaseOrderType`] ノードを右クリックし、 **[すべての参照の表示]** を選択します。

     `purchaseOrder` ノードが強調表示されます。

3. `purchaseOrder` ノードをグラフ ビューにドラッグします。

     `purchaseOrder` ノードおよび `PurchaseOrderType` ノードがグラフ ビューのデザイン サーフェイスに並べて表示されます。 2 つのノードは関連があるため (`purchaseOrder` 要素は `PurchaseOrderType` 型)、これらの間に矢印が引かれます。

## <a name="to-add-nodes-using-the-schema-explorer-search-capability"></a>スキーマ エクスプローラーの検索機能を使用してノードを追加するには

1. [XML エクスプローラー](../xml-tools/xml-schema-explorer.md)のツールバーの [検索] テキストボックスに「purchaseOrder」と入力し、[検索] ボタンをクリックします。

     ![XML スキーマ エクスプローラー キーワード検索](../xml-tools/media/schemaexplorersearch.gif)

     検索結果は、 **XML スキーマエクスプローラー**で強調表示され、垂直スクロールバーのティックでマークされます。

2. 概要結果ペインの [強調表示された**ノードをワークスペースに追加**] ボタンをクリックして、ワークスペースに検索結果を追加します。

     ![XML スキーマ エクスプローラー検索結果](../xml-tools/media/schemaexplorersearchresult.gif)

     [@No__t_0] ノードと [`PurchaseOrderType`] ノードは、[グラフビュー](../xml-tools/graph-view.md)のデザイン画面に表示されます。 2 つのノードは関連があるため (`purchaseOrder` 要素は `PurchaseOrderType` 型)、これらの間に矢印が引かれます。

## <a name="see-also"></a>関連項目

- [XML スキーマ エクスプローラー](../xml-tools/xml-schema-explorer.md)