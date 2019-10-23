---
title: 'XML スキーマデザイナー: グラフビューを使用したスキーマセットの概要の取得'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c0df4b0d-52ef-4a6c-9676-1d8311aad7c7
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b8acc2ff6a41f7057818c4a7659f2aa9d07c8bac
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72651179"
---
# <a name="how-to-get-an-overview-of-a-schema-set-using-the-graph-view"></a>方法: グラフビューを使用してスキーマセットの概要を取得する

このトピックでは、[グラフビュー](../xml-tools/graph-view.md)を使用して、スキーマセット内のノードの概要とノード間のリレーションシップを表示する方法について説明します。

## <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>新しい XSD ファイルを作成してコンテンツ モデル ビューにルート要素を表示するには

1. 新しい XML スキーマファイルを作成し、ファイルを*リレーションシップ .xsd*として保存します。

2. [XML エディターを使用して、スタートビューの**基になる Xml スキーマファイルを表示および編集する**] リンクをクリックします。

3. [「サンプル xml スキーマ: リレーションシップ](../xml-tools/sample-xsd-file-relationships.md)」から xml スキーマのサンプルコードをコピーして貼り付け、新しい XSD ファイルに既定で追加されたコードを置き換えます。

4. XML エディター内の任意の場所を右クリックし、 **[ビューデザイナー]** をクリックします。

5. **XSD ツールバー**からグラフビューを選択します。

6. **XML スキーマエクスプローラー**で **[スキーマセット]** ノードを選択し、グラフビューのデザイン画面にノードをドラッグします。 すべてのグローバル ノードが表示され、リレーションシップを持つノード間に矢印が引かれます。

     ![グラフ ビュー](../xml-tools/media/relationshipingraphview.gif)

7. デザイン サーフェイスでノードをクリックし、階層リンク バーで選択したノードが存在するスキーマ セットの場所を確認します。

8. デザイン画面で要素ノードを Rick クリックし、 **[サンプル xml の生成]** を選択して xml インスタンスドキュメントを表示します。