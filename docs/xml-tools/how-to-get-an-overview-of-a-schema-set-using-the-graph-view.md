---
title: XML スキーマ デザイナー:グラフ ビューを使用してスキーマ セットの概要を取得します。
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c0df4b0d-52ef-4a6c-9676-1d8311aad7c7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e0a0fc62a0d6dfe772a550f33cafa02bc5bc1bf3
ms.sourcegitcommit: ba5e072c9fedeff625a1332f22dcf3644d019f51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66432159"
---
# <a name="how-to-get-an-overview-of-a-schema-set-using-the-graph-view"></a>方法: グラフ ビューを使用して設定のスキーマの概要します。

このトピックでは、使用する方法を説明します、[グラフ ビュー](../xml-tools/graph-view.md)スキーマ セットと、ノード間のリレーションシップ内のノードの高度なビューを表示します。

## <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>新しい XSD ファイルを作成してコンテンツ モデル ビューにルート要素を表示するには

1. 新しい XML スキーマ ファイルを作成し、ファイルに保存します*Relationships.xsd*します。

2. をクリックして、**使用して XML エディターを表示および基になる XML スキーマ ファイルの編集を**スタート ビューにリンクします。

3. XML スキーマのサンプル コードをコピー[サンプルの XML スキーマ: リレーションシップ](../xml-tools/sample-xsd-file-relationships.md)してそれを既定では、新しい XSD ファイルに追加されたコードに置き換えます。

4. XML エディター内を右クリックし、選択**ビュー デザイナー**します。

5. グラフ ビューの選択、 **XSD ツールバー**します。

6. 選択**スキーマ セット**内のノード、 **XML スキーマ エクスプ ローラー**ノードをグラフ ビューのデザイン画面にドラッグします。 すべてのグローバル ノードが表示され、リレーションシップを持つノード間に矢印が引かれます。

     ![グラフ ビュー](../xml-tools/media/relationshipingraphview.gif)

7. デザイン サーフェイスでノードをクリックし、階層リンク バーで選択したノードが存在するスキーマ セットの場所を確認します。

8. デザイン サーフェスと選択の任意の要素ノードを右クリック**サンプル XML の生成**に XML インスタンス ドキュメントを参照してください。