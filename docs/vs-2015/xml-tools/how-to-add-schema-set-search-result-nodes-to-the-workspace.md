---
title: '方法: スキーマ セットの検索結果のノードをワークスペースに追加します |。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: ff33b3cc-4db9-4b4e-9378-b45ed5999b18
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4fc312d4120ef8d1d0f2deb5acd3ce581e878570
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63447115"
---
# <a name="how-to-add-schema-set-search-result-nodes-to-the-workspace"></a>方法: スキーマ セットの検索結果のノードをワークスペースに追加する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックでは、キーワード検索の結果、XML スキーマ エクスプローラーに強調表示されたノードをワークスペースに追加する方法について説明します。  
  
> [!NOTE]
> グローバル ノードだけを追加することができます、[ワークスペース](../xml-tools/xml-schema-designer-workspace.md)します。  
  
 この例は、サンプルを使用して[購買発注書スキーマ](../xml-tools/sample-xsd-file-purchase-order-schema.md)します。  
  
### <a name="to-add-schema-set-result-nodes"></a>スキーマ セットの検索結果のノードを追加するには  
  
1. 次の手順では、[方法。作成し、XSD スキーマ ファイルを編集する](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)します。  
  
2. 検索 テキスト ボックスに「purchaseOrder」を入力、 [XML エクスプ ローラー](../xml-tools/xml-schema-explorer.md)ツールバーおよび検索ボタンをクリックします。  
  
     ![XML スキーマ エクスプ ローラー キーワード検索](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")  
  
     検索結果が XML スキーマ エクスプローラーで強調表示され、垂直スクロール バーのチックでマークされます。  
  
3. クリックして、ワークスペースに検索結果を追加、**強調表示されたノードをワークスペースに追加**概要結果ペインでボタンをクリックします。  
  
     ![XML スキーマ エクスプ ローラーの検索結果](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")  
  
     `purchaseOrder`ノードと`PurchaseOrderType`のデザイン画面で、ノードが互いの横に表示、[グラフ ビュー](../xml-tools/graph-view.md)します。 2 つのノードは関連があるため (`purchaseOrder` 要素は `PurchaseOrderType` 型)、これらの間に矢印が引かれます。
