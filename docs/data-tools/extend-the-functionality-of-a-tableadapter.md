---
title: TableAdapter の機能を拡張する
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- data [Visual Studio], extending TableAdapters
- TableAdapters, adding functionality
ms.assetid: 418249c8-c7f3-47ef-a94c-744cb6fe6aaf
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 6df50eb1f8a4d722a0140fd37a6ff0c0d7474a39
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55955272"
---
# <a name="extend-the-functionality-of-a-tableadapter"></a>TableAdapter の機能を拡張する

TableAdapter の機能を拡張するには、TableAdapter の部分クラス ファイルにコードを追加します。

TableAdapter に変更されたときに TableAdapter を定義するコードが再生成、**データセット デザイナー**、またはウィザードが、TableAdapter の構成を変更します。 コードが、TableAdapter の再生成中に削除されないようにするには、TableAdapter の部分クラス ファイルにコードを追加します。

部分クラスは、特定のクラスを複数の物理ファイルに分割するためのコードを使用します。 詳細については、次を参照してください。[部分](/dotnet/visual-basic/language-reference/modifiers/partial)または[partial (型)](/dotnet/csharp/language-reference/keywords/partial-type)します。

## <a name="locate-tableadapters-in-code"></a>コード内で Tableadapter を検索します。

Tableadapter は設計されています中に、**データセット デザイナー**、生成された TableAdapter クラスの入れ子になったクラスでない<xref:System.Data.DataSet>します。 Tableadapter は、TableAdapter の関連付けられているデータセットの名前に基づいて、名前空間に配置されます。 たとえば、アプリケーションには、という名前のデータセットが含まれている場合`HRDataSet`、Tableadapter に配置されます、`HRDataSetTableAdapters`名前空間。 (名前付け規則がこのパターンに従います: *DatasetName* + `TableAdapters`)。

次の例では、という名前の TableAdapter`CustomersTableAdapter`のプロジェクトでは、`NorthwindDataSet`します。

### <a name="to-create-a-partial-class-for-a-tableadapter"></a>TableAdapter の部分クラスを作成するには

1.  移動して、プロジェクトに新しいクラスを追加、**プロジェクト**メニュー**クラスの追加**します。

2.  クラスに `CustomersTableAdapterExtended` という名前を付けます。

3.  **[追加]** を選びます。

4.  正しい名前空間と、プロジェクトの名前を部分クラスとしては、次のようにコードを置き換えます。

     [!code-csharp[VbRaddataTableAdapters#2](../data-tools/codesnippet/CSharp/extend-the-functionality-of-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataTableAdapters#2](../data-tools/codesnippet/VisualBasic/extend-the-functionality-of-a-tableadapter_1.vb)]

## <a name="see-also"></a>関連項目

- [TableAdapters を使用してデータセットを入力する](../data-tools/fill-datasets-by-using-tableadapters.md)