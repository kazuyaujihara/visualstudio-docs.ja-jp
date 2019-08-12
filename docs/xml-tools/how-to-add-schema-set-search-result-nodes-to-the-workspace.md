---
title: XML スキーマセットの検索結果ノードをワークスペースに追加する
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ff33b3cc-4db9-4b4e-9378-b45ed5999b18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c2718c08b36ff9ef3ca8ae06f7d511cacb8fa73c
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923654"
---
# <a name="how-to-add-schema-set-search-result-nodes-to-the-workspace"></a>方法: スキーマ セットの検索結果のノードをワークスペースに追加する

このトピックでは、 **XML スキーマエクスプローラー**で強調表示されているノードを、ワークスペースでのキーワード検索の結果として追加する方法について説明します。

> [!NOTE]
> [ワークスペース](../xml-tools/xml-schema-designer-workspace.md)に追加できるのは、グローバルノードだけです。

この例では、サンプルの注文[書スキーマ](../xml-tools/sample-xsd-file-purchase-order-schema.md)を使用します。

## <a name="to-add-schema-set-result-nodes"></a>スキーマ セットの検索結果のノードを追加するには

1. [「方法:XSD スキーマファイル](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)を作成および編集します。

2. [XML エクスプローラー](../xml-tools/xml-schema-explorer.md)のツールバーの [検索] テキストボックスに「purchaseOrder」と入力し、[検索] ボタンをクリックします。

     ![XML スキーマ エクスプローラー キーワード検索](../xml-tools/media/schemaexplorersearch.gif)

     検索結果は、 **XML スキーマエクスプローラー**で強調表示され、垂直スクロールバーのティックでマークされます。

3. 概要結果ペインの [強調表示された**ノードをワークスペースに追加**] ボタンをクリックして、ワークスペースに検索結果を追加します。

     ![XML スキーマ エクスプローラー検索結果](../xml-tools/media/schemaexplorersearchresult.gif)

     ノードとノードは、[グラフビュー](../xml-tools/graph-view.md)のデザイン画面で相互に表示されます。 `PurchaseOrderType` `purchaseOrder` 2 つのノードは関連があるため (`purchaseOrder` 要素は `PurchaseOrderType` 型)、これらの間に矢印が引かれます。