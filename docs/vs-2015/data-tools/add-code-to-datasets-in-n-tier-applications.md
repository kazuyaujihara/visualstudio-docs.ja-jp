---
title: N 層アプリケーションでのデータセットにコードを追加 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- n-tier applications, extending datasets
ms.assetid: d43c2ccd-4902-43d8-b1a8-d10ca5d3210c
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 6c788e422ea8613b77d7d0c0460d7c026916baa3
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697153"
---
# <a name="add-code-to-datasets-in-n-tier-applications"></a>n 層アプリケーションのデータセットにコードを追加する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

データセットの機能を拡張するには、データセットの部分クラス ファイルを作成し、コードを追加 (コードを追加するのではなく、 *DatasetName*します。Dataset.Designer ファイル)。 部分クラスには、特定のクラスを複数の物理ファイルに分割するためのコードが有効にします。 詳細については、次を参照してください。[部分](https://msdn.microsoft.com/library/7adaef80-f435-46e1-970a-269fff63b448)または[部分クラスとメソッド](https://msdn.microsoft.com/library/804cecb7-62db-4f97-a99f-60975bd59fa1)します。

データセット定義を変更するたびに、データセットを定義するコードが生成されます。 このコードは、データセットの構成を変更するウィザードの実行中に変更するときにも生成されます。 コードが、データセットの再生成中に削除されないようにするには、データセットの部分クラス ファイルにコードを追加します。

既定では、データセットと `TableAdapter` コードを分離すると、結果としてプロジェクトごとに別個のクラス ファイルが生成されます。 元のプロジェクトに、filenamed *DatasetName*します。(または*DatasetName*します。Designer.cs) を含む、`TableAdapter`コード。 指定されているプロジェクト、 **Dataset プロジェクト**プロパティという名前のファイルは、 *DatasetName*します。DataSet.Designer.vb (または*DatasetName*します。DataSet.Designer.cs)。このファイルには、データセット コードが含まれています。

> [!NOTE]
> データセットを分離する場合と`TableAdapter`s (設定して、 **DataSet プロジェクト**プロパティ)、プロジェクト内の既存のデータセット部分クラスが自動的に移動しません。 既存のデータセット部分クラスは、手動でデータセット プロジェクトに移動する必要があります。

> [!NOTE]
> 検証コードを追加する必要があると、データセット デザイナーが生成するための機能を提供します<xref:System.Data.DataTable.ColumnChanging>と<xref:System.Data.DataTable.RowChanging>イベント ハンドラー。 詳細については、次を参照してください。 [n 層データセットに検証を追加](../data-tools/add-validation-to-an-n-tier-dataset.md)します。

## <a name="add-code-to-datasets-in-n-tier-applications"></a>n 層アプリケーションのデータセットにコードを追加する

1. .Xsd ファイル (データセット) を含むプロジェクトを見つけます。

2. 選択、 **.xsd**ファイル データセットを開きます。

3. コード (タイトル バーのテーブル名) を追加し、選択するデータ テーブルを右クリックして**コードの表示**します。

     部分クラスが作成され、コード エディターで開きます。

4. 部分クラス宣言内でコードを追加します。

     次の例は、NorthwindDataSet 内 CustomersDataTable にコードを追加する場所を示しています。

    ```vb
    Partial Public Class CustomersDataTable
        ' Add code here to add functionality
        ' to the CustomersDataTable.
    End Class
    ```

    ```csharp
    partial class CustomersDataTable
    {
        // Add code here to add functionality
        // to the CustomersDataTable.
    }
    ```

## <a name="see-also"></a>関連項目

- [n 層データ アプリケーションの概要](../data-tools/n-tier-data-applications-overview.md)
- [n 層アプリケーションの TableAdapters にコードを追加する](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md)
- [Tableadapter](https://msdn.microsoft.com/library/09416de9-134c-4dc7-8262-6c8d81e3f364)
- [TableAdapterManager の概要](https://msdn.microsoft.com/library/33076d42-6b41-491a-ac11-6c6339aea650)
- [階層更新の概要](https://msdn.microsoft.com/library/c4f8e8b9-e4a5-4a02-8462-d03d1e8222d6)
- [Visual Studio のデータセット ツール](../data-tools/dataset-tools-in-visual-studio.md)