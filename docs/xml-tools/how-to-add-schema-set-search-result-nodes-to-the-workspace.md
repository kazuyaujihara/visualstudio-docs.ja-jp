---
title: XML スキーマセットの検索結果ノードをワークスペースに追加する
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ff33b3cc-4db9-4b4e-9378-b45ed5999b18
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: be024ac139d2b420f56b14158afd33ae5b7e917d
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72646024"
---
# <a name="how-to-add-schema-set-search-result-nodes-to-the-workspace"></a>方法: ワークスペースにスキーマセットの検索結果ノードを追加する

このトピックでは、 **XML スキーマエクスプローラー**で強調表示されているノードを、ワークスペースでのキーワード検索の結果として追加する方法について説明します。

> [!NOTE]
> [ワークスペース](../xml-tools/xml-schema-designer-workspace.md)に追加できるのは、グローバルノードだけです。

この例では、サンプルの注文[書スキーマ](../xml-tools/sample-xsd-file-purchase-order-schema.md)を使用します。

## <a name="to-add-schema-set-result-nodes"></a>スキーマ セットの検索結果のノードを追加するには

1. [「方法: XSD スキーマファイルを作成および編集する](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)」の手順に従います。

2. [XML エクスプローラー](../xml-tools/xml-schema-explorer.md)のツールバーの [検索] テキストボックスに「purchaseOrder」と入力し、[検索] ボタンをクリックします。

     ![XML スキーマ エクスプローラー キーワード検索](../xml-tools/media/schemaexplorersearch.gif)

     検索結果は、 **XML スキーマエクスプローラー**で強調表示され、垂直スクロールバーのティックでマークされます。

3. 概要結果ペインの [強調表示された**ノードをワークスペースに追加**] ボタンをクリックして、ワークスペースに検索結果を追加します。

     ![XML スキーマ エクスプローラー検索結果](../xml-tools/media/schemaexplorersearchresult.gif)

     [@No__t_0] ノードと [`PurchaseOrderType`] ノードは、[グラフビュー](../xml-tools/graph-view.md)のデザイン画面に表示されます。 2 つのノードは関連があるため (`purchaseOrder` 要素は `PurchaseOrderType` 型)、これらの間に矢印が引かれます。