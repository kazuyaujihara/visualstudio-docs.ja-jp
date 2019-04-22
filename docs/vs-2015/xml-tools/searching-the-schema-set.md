---
title: スキーマ セットの検索 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: ec1395e0-d03c-4130-810d-f2db656937bd
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 98ed22a9a6e570c5e47c6b51ddf4486334205a0f
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59661270"
---
# <a name="searching-the-schema-set"></a>スキーマ セットの検索
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

XML スキーマ エクスプローラーでは、次の方法でスキーマ セットを検索できます。  
  
-   キーワード検索  
  
-   スキーマ固有の検索  
  
## <a name="keyword-search"></a>キーワード検索  
 内の部分文字列を入力してキーワード検索を実行する、**検索 SchemaSet** XML スキーマ エクスプ ローラーのツールバーのテキスト ボックス。  
  
 ![XML スキーマ エクスプ ローラー キーワード検索](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")  
  
 XML スキーマ エクスプローラーは、次のようにスキーマ セットを検索します。  
  
-   指定したキーワードに一致する `name` 属性または `ref` 属性。 これを使用すると、要素、属性、型などを名前で検索することができます。  
  
-   include ステートメントの `schemaLocation` 属性。  
  
-   import ステートメントの `namespace` 属性。  
  
## <a name="schema-specific-search"></a>スキーマ固有の検索  
 XML スキーマ エクスプローラーには、XML スキーマ エクスプローラーのコンテキスト メニューを使用してアクセスできる組み込みの検索機能もあります。 使用できるコンテキスト メニューの詳細については、次を参照してください。[コンテキスト メニュー](../xml-tools/context-menus-xml-schema-explorer.md)します。 スタート ビューからスキーマ固有の検索を実行することもできます。詳細については、「スキーマ セットの詳細」セクションを参照してください、[スタート ビュー](../xml-tools/start-view.md)トピック。  
  
## <a name="displaying-and-navigating-search-results"></a>検索結果の表示および移動  
 検索が終了すると、ツール バーに概要結果ペインが追加され、検索結果が表示されます。 検索結果は XML スキーマ エクスプローラーでも強調表示され、垂直スクロール バーの目盛りでマークされます。 使用して、検索結果を移動することができます、**次の検索結果に移動して**と**前の検索結果に移動して**概要結果ペインはキーボードのキーを使用して、XML スキーマ エクスプ ローラー ツールバーのボタンF3 キーおよび shift + f3;または、スクロール バーの目盛りをクリックします。  
  
 クリックして、ワークスペースに検索結果を追加することができます、**強調表示されたノードをワークスペースに追加**概要結果ペインでボタンをクリックします。  
  
 ![XML スキーマ エクスプ ローラーの検索結果](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")  
  
## <a name="clearing-search-results"></a>検索結果のクリア  
 検索結果をクリアする] をクリックして、 **x** XML スキーマ エクスプ ローラー検索ツールバーの [概要結果ペインでボタンをクリックします。  
  
## <a name="see-also"></a>関連項目  
 [XML スキーマ エクスプローラー](../xml-tools/xml-schema-explorer.md)
