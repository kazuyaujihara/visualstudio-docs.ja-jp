---
title: '方法: グラフ ビューを使用してスキーマ セットの概要を説明 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: c0df4b0d-52ef-4a6c-9676-1d8311aad7c7
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4c2eb0127c25e2c6702e5805d261a53a993914c6
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59653256"
---
# <a name="how-to-get-an-overview-of-a-schema-set-using-the-graph-view"></a>方法: グラフ ビューを使用してスキーマ セットの概要を表示する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックでは、使用する方法を説明します、[グラフ ビュー](../xml-tools/graph-view.md)スキーマ セットと、ノード間のリレーションシップ内のノードの高度なビューを表示します。  
  
### <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>新しい XSD ファイルを作成してコンテンツ モデル ビューにルート要素を表示するには  
  
1.  新しい XML スキーマ ファイルを作成して、Relationships.xsd という名前でファイルを保存します。  
  
2.  をクリックして、 **XML エディターを使用して表示および基になる XML スキーマ ファイルを編集して**スタート ビューにリンクします。  
  
3.  XML スキーマのサンプル コードをコピー[サンプルの XML スキーマ。リレーションシップ](../xml-tools/sample-xsd-file-relationships.md)してそれを既定では、新しい XSD ファイルに追加されたコードに置き換えます。  
  
4.  XML エディター内を右クリックし、選択**ビュー デザイナー**します。  
  
5.  XSD ツール バーからグラフ ビューを選択します。  
  
6.  選択**スキーマ セット**グラフ ビューのデザイン サーフェイスには、XML スキーマ エクスプ ローラーとドラッグ、ノード内のノード。 すべてのグローバル ノードが表示され、リレーションシップを持つノード間に矢印が引かれます。  
  
     ![グラフ ビュー](../xml-tools/media/relationshipingraphview.gif "RelationshipInGraphView")  
  
7.  デザイン サーフェイスでノードをクリックし、階層リンク バーで選択したノードが存在するスキーマ セットの場所を確認します。  
  
8.  選択し、画面のデザイン上の任意の要素ノードを右クリック**サンプル XML の生成**に XML インスタンス ドキュメントを参照してください。
