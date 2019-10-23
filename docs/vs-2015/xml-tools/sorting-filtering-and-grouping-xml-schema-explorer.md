---
title: 並べ替え、フィルター処理、およびグループ化 (XML スキーマエクスプローラー) |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 4a914de0-9ffc-4526-9603-92e460e52513
caps.latest.revision: 11
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 99c28842a92ab598ff196e80fc96678c256e4db8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72656148"
---
# <a name="sorting-filtering-and-grouping-xml-schema-explorer"></a>並べ替え、フィルター処理、およびグループ化 (XML スキーマ エクスプローラー)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックでは、XML スキーマエクスプローラーのツールバーの **[並べ替え、フィルター処理、およびグループ化のオプション]** メニューで使用できるオプションについて説明します。

## <a name="filter-options"></a>フィルター オプション
 次のフィルター オプションがあります。 既定では、 **[名前空間の表示]** オプションと **[スキーマファイルを表示]** する オプションが選択されています。

- **名前空間を表示**します。

- **スキーマファイルを表示**します。

- [ **Show コンポジター (sequence/choice/all)] を選択**します。

## <a name="sorting-options"></a>並べ替えオプション
 次の並べ替えオプションがあります。 既定値は、**種類で並べ替え**です。 ファイルと名前空間には、[種類で並べ替え] オプションと [名前で並べ替え] オプションは適用されません。

- **種類で並べ替え**ます。

- **名前で並べ替え**ます。

- **ドキュメントの順序**。

### <a name="sort-by-type"></a>[種類で並べ替え]
 **[種類で並べ替え]** オプションが選択されている場合、グローバルノードは次の順序で並べ替えられます。 さらに、各グループ内でアルファベット順に並べ替えられます。

1. `import` ノード

2. `include` ノード

3. `redefine` ノード

4. `attribute` ノード

5. `attributeGroup` ノード

6. `complexType` ノード

7. `simpleType` ノード

8. `element` ノード

9. `group` ノード

### <a name="sort-by-name"></a>[名前で並べ替え]
 **[名前で並べ替え]** オプションが選択されている場合、グローバルノードは次の順序で並べ替えられます。

1. `import` ノード (名前空間のアルファベット順)

2. `include` ノード (`schemaLocation` 属性のアルファベット順)

3. `redefine` ノード (`schemaLocation` 属性のアルファベット順)

4. その他のグローバル ノード (アルファベット順)

### <a name="document-order"></a>[ドキュメントの順序]
 **[ドキュメントの順序]** オプションは、 **[スキーマファイルの表示]** オプションが選択されている場合に使用できます。 **ドキュメントの順序**が選択されている場合、グローバルノードはスキーマファイルに表示される順序で表示されます。

## <a name="persisting-sortfilter-options"></a>並べ替え/フィルター オプションの保存
 設定の変更時に開かれていたソリューションやファイルにかかわらず、並べ替え、フィルター処理、およびグループ化のオプションは各ユーザーのレジストリに保存されます。
