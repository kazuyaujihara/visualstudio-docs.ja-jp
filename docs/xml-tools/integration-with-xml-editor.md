---
title: XML エディターと XML スキーマ デザイナーの統合
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 43d7a8e6-bd94-4407-a800-15a145c74223
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: faad46c6ac2686de69fcb33f2fb482bdb0f4fe00
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57525134"
---
# <a name="integration-with-xml-editor"></a>XML エディターとの統合

XML スキーマ デザイナーは、XML エディターと統合されます。 変更を反映する XML エディターで XSD ファイルを変更する場合、 [XML スキーマ エクスプ ローラー](../xml-tools/xml-schema-explorer.md)します。 ある場合、[グラフ ビュー](../xml-tools/graph-view.md)または[コンテンツ モデル ビュー](../xml-tools/content-model-view.md)開く、変更も反映されますがあります。 次の方法で XML スキーマ デザイナーと XML エディター間を移動することができます。

-   XML エディターでノードを右クリックし、選択**XML スキーマ エクスプ ローラーで表示する**します。

-   グラフ ビューで、 **XML スキーマ エクスプ ローラー**ノードをダブルクリック、またはノードを右クリックし、選択**コードの表示**します。 コンテンツ モデル ビューでは、ノードを右クリックして**コードの表示**します。

次のスクリーン ショットで開かれている XML スキーマ、 **XML スキーマ エクスプ ローラー**します。 **XML スキーマ エクスプ ローラー**ツリー ビューでスキーマ セットが表示されます。 XML エディターで現在アクティブなノードのテキスト ビューが表示されます、 **XML スキーマ エクスプ ローラー**します。

![XSDDesignerWithXMLEditor](../xml-tools/media/xsddesignerwithxmleditor.gif)

場合によって、XML エディターとグラフィカルなデザイナーをサイド バイ サイドでコードを表示することをお勧めします。 を同時に両方のファイルを表示する、XML エディター内を右クリックし、選択**ビュー デザイナー**します。 Visual Studio Windows メニューで、次のように選択します。**新しい水平 (または垂直) タブ グループ**します。

![XSDDesignerWithXMLEditorAndCMV](../xml-tools/media/xsddesignerwithxmleditorandcmv.gif)

## <a name="see-also"></a>関連項目

- [XML スキーマ エクスプローラー](../xml-tools/xml-schema-explorer.md)