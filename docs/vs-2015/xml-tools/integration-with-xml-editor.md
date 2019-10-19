---
title: XML エディターとの統合 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 43d7a8e6-bd94-4407-a800-15a145c74223
caps.latest.revision: 10
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 8c0d1088e9932613466209ef8517ac5035c0b613
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72656252"
---
# <a name="integration-with-xml-editor"></a>XML エディターとの統合
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

XML スキーマ デザイナーは、XML エディターと統合されています。 XML エディターで XSD ファイルを変更すると、 [Xml スキーマエクスプローラー](../xml-tools/xml-schema-explorer.md)に変更が反映されます。 [グラフビュー](../xml-tools/graph-view.md)または[コンテンツモデルビュー](../xml-tools/content-model-view.md)が開いている場合は、そこにも変更が反映されます。 次の方法を使用して XML スキーマ デザイナーと XML エディターの間を移動できます。

- XML エディターでノードを右クリックし、 **[Xml スキーマエクスプローラーで表示]** をクリックします。

- グラフビューと XML スキーマエクスプローラーで、ノードをダブルクリックするか、ノードを右クリックして [コードの**表示**] を選択します。 コンテンツモデルビューで、ノードを右クリックし、 **[コードの表示]** を選択します。

  次のスクリーン ショットは、XML スキーマが表示されている XML スキーマ エクスプローラーを示しています。 XML スキーマ エクスプローラーでは、スキーマ セットがツリー ビューに表示されます。 XML エディターには、XML スキーマ エクスプローラーで現在アクティブになっているノードのテキスト ビューが表示されます。

  ![XSDDesignerWithXMLEditor](../xml-tools/media/xsddesignerwithxmleditor.gif "XSDDesignerWithXMLEditor")

  場合によっては、XML エディターとグラフィカルなデザイナーのコードを並べて表示すると便利です。 両方のファイルを同時に表示するには、XML エディター内の任意の場所を右クリックし、 **[デザイナーの表示]** をクリックします。 Visual Studio の Windows メニューで、**水平 (または垂直) の新しいタブグループ** を選択します。

  ![Xsdデザイナ Withxmleditorandcmv](../xml-tools/media/xsddesignerwithxmleditorandcmv.gif "XSDDesignerWithXMLEditorAndCMV")

## <a name="see-also"></a>参照
 [XML スキーマ エクスプローラー](../xml-tools/xml-schema-explorer.md)
