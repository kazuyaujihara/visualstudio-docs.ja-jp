---
title: O/R デザイナーの概要
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 45e477c0-5c6b-41f9-b2d0-2808fb4f6537
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 9511f2101c8dbac0ae8a9ba9e08f9a4f22067c3a
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71252936"
---
# <a name="linq-to-sql-tools-in-visual-studio"></a>Visual Studio の LINQ to SQL ツール

LINQ to SQL は、Microsoft によってリリースされた最初のオブジェクトリレーショナルマッピングテクノロジです。 これは基本的なシナリオで適切に動作し、Visual Studio で引き続きサポートされますが、アクティブな開発ではなくなります。 LINQ to SQL は、既に使用しているレガシアプリケーションを維持する場合や、SQL Server を使用し、複数テーブルのマッピングを必要としない単純なアプリケーションの場合に使用します。 一般に、オブジェクトリレーショナルマッパーレイヤーが必要な場合は、新しいアプリケーションで Entity Framework を使用する必要があります。

Visual Studio では、**オブジェクトリレーショナルデザイナー** (**O/R デザイナー**) を使用して SQL テーブルを表す LINQ to SQL クラスを作成します。

**O/R デザイナー**のデザイン画面には、左側の [エンティティ] ペインと右側の [メソッド] ペインの2つの異なる領域があります。 エンティティ ペインは、エンティティ クラス、関連付け、および継承階層を表示するメインのデザイン サーフェイスです。 メソッド ペインは、ストアド プロシージャと関数にマッピングされる <xref:System.Data.Linq.DataContext> のメソッドを表示するデザイン サーフェイスです。

**O/R デザイナー**には、データベース内のオブジェクトに基づくエンティティクラスと関連付け (リレーションシップ) を[LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)作成するためのビジュアルデザインサーフェイスが用意されています。 つまり、 **O/R デザイナー**は、データベース内のオブジェクトにマップされるオブジェクトモデルをアプリケーションに作成します。 また、エンティティクラスとデータベースの<xref:System.Data.Linq.DataContext>間でデータを送受信する、厳密に型指定されたを生成します。 **O/R デザイナー**には、データを返し、エンティティクラスを設定<xref:System.Data.Linq.DataContext>するためのストアドプロシージャと関数をメソッドにマップする機能も用意されています。 最後に、 **O/R デザイナー**は、エンティティクラス間の継承関係を設計する機能を提供します。

## <a name="open-the-or-designer"></a>O/R デザイナーを開く

LINQ to SQL エンティティモデルをプロジェクトに追加するには、[**プロジェクト** > ] **[新しい項目の追加]** の順に選択し、プロジェクト項目の一覧から **[LINQ to SQL クラス]** を選択します。

![LINQ to SQL クラス](../data-tools/media/raddata-linq-to-sql-classes.png)

Visual Studio によって *.dbml*ファイルが作成され、ソリューションに追加されます。 これは、XML マッピングファイルとそれに関連するコードファイルです。

![ソリューションエクスプローラーの LINQ to SQL クラス](../data-tools/media/raddata-linq-to-sql-classes-in-solution-explorer.png)

*.Dbml*ファイルを選択すると、Visual Studio には、モデルを視覚的に作成できる**O/R デザイナー**画面が表示されます。 次の図は、Northwind `Customers`と`Orders`テーブルが**サーバーエクスプローラー**からドラッグされた後のデザイナーを示しています。 テーブル間のリレーションシップに注意してください。

![LINQ to SQL デザイナー](../data-tools/media/raddata-linq-to-sql-designer.png)

> [!IMPORTANT]
> **O/R デザイナー**は、1:1 のマッピング関係のみをサポートするため、単純なオブジェクトリレーショナルマッパーです。 つまり、エンティティ クラスには、データベース テーブルまたはビューとの 1:1 のマッピング関係しか持たせることができません。 結合テーブルへのエンティティクラスのマッピングなど、複雑なマッピングはサポートされていません。複雑なマッピングには Entity Framework を使用します。 また、デザイナーは一方向のコード ジェネレーターです。 つまり、デザイナー サーフェイスに加えた変更だけがコード ファイルに反映されます。 コードファイルに対する手動の変更は、 **O/R デザイナー**には反映されません。 コード ファイルに手動で加えた変更は、デザイナーを保存してコードを再生成するときに上書きされます。 ユーザーコードを追加し、 **O/R デザイナー**によって生成されるクラスを拡張する方法[の詳細については、「」を参照してください。O/R デザイナー](../data-tools/how-to-extend-code-generated-by-the-o-r-designer.md)によって生成されたコードを拡張します。

## <a name="create-and-configure-the-datacontext"></a>DataContext の作成と構成

**LINQ to SQL クラス**項目をプロジェクトに追加し、 **O/R デザイナー**を開くと、空のデザインサーフェイスは、構成の<xref:System.Data.Linq.DataContext>準備が整っている空のを表します。 <xref:System.Data.Linq.DataContext> は、デザイン サーフェイスにドラッグされた最初の項目から提供される接続情報で構成されます。 したがって、<xref:System.Data.Linq.DataContext> は、デザイン サーフェイスにドロップされた最初の項目の接続情報によって構成されます。 クラスの<xref:System.Data.Linq.DataContext>詳細については、「 [DataContext メソッド (O/R デザイナー)](../data-tools/datacontext-methods-o-r-designer.md)」を参照してください。

## <a name="create-entity-classes-that-map-to-database-tables-and-views"></a>データベースのテーブルおよびビューにマップするエンティティクラスを作成する

テーブルとビューにマップされたエンティティクラスを作成するには、データベースのテーブルとビューを**サーバーエクスプローラー**から、または**データベースエクスプローラー**を**O/R デザイナー**にドラッグします。 前のセクションで示したように、<xref:System.Data.Linq.DataContext> は、デザイン サーフェイスにドラッグされる最初の項目が提供する接続情報で構成されます。 別の接続を使用する後続の項目が**O/R デザイナー**に追加されている場合は、 <xref:System.Data.Linq.DataContext>の接続を変更できます。 詳細については、「[方法 :テーブルとビューにマップされた LINQ to SQL クラスを作成する (O/R デザイナー)](../data-tools/how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)」を参照してください。

## <a name="create-datacontext-methods-that-call-stored-procedures-and-functions"></a>ストアドプロシージャおよび関数を呼び出す DataContext メソッドを作成する

ストアドプロシージャおよび<xref:System.Data.Linq.DataContext>関数を**サーバーエクスプローラー**または**データベースエクスプローラー**から**O/R デザイナー**にドラッグすることによって、ストアドプロシージャおよび関数を呼び出す (マップされる) メソッドを作成できます。 ストアドプロシージャと関数は、 <xref:System.Data.Linq.DataContext>のメソッドとして**O/R デザイナー**に追加されます。

> [!NOTE]
> ストアドプロシージャおよび関数を**サーバーエクスプローラー**または**データベースエクスプローラー**から**O/R デザイナー**にドラッグすると、生成さ<xref:System.Data.Linq.DataContext>れたメソッドの戻り値の型は、項目をドロップする場所によって異なります。 詳細については、「 [DataContext メソッド (O/R デザイナー)](../data-tools/datacontext-methods-o-r-designer.md)」を参照してください。

## <a name="configure-a-datacontext-to-use-stored-procedures-to-save-data-between-entity-classes-and-a-database"></a>ストアドプロシージャを使用してエンティティクラスとデータベース間のデータを保存するように DataContext を構成する

前に述べたように、ストアド プロシージャと関数を呼び出す <xref:System.Data.Linq.DataContext> のメソッドを作成できます。 また、挿入、更新、および削除を実行する既定の LINQ to SQL 実行時の動作に使用されるストアドプロシージャを割り当てることもできます。 詳細については、「[方法 :更新、挿入、および削除を実行するストアド プロシージャを割り当てる (O/R デザイナー)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)」を参照してください。

## <a name="inheritance-and-the-or-designer"></a>継承と O/R デザイナー

他のオブジェクトと同様に、LINQ to SQL クラスは継承を使用し、他のクラスから派生させることができます。 データベースでは、継承関係が複数の方法で作成されます。 **O/R デザイナー**は、リレーショナルシステムに実装されることが多いため、単一テーブル継承の概念をサポートしています。 詳細については、「[方法 :O/R デザイナーを使用して継承を構成する](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)」を参照してください。

## <a name="linq-to-sql-queries"></a>LINQ to SQL クエリ

**O/R デザイナー**によって作成されたエンティティクラスは、[統合言語クエリ (LINQ)](/dotnet/csharp/linq/)で使用できるように設計されています。 詳細については、「[方法 :情報](/dotnet/framework/data/adonet/sql/linq/how-to-query-for-information)を照会します。

## <a name="separate-the-generated-datacontext-and-entity-class-code-into-different-namespaces"></a>生成された DataContext とエンティティクラスコードを別々の名前空間に分割する

**O/R デザイナー**では、 <xref:System.Data.Linq.DataContext>に**コンテキスト名前空間**と**エンティティ名前空間**のプロパティが用意されています。 これらのプロパティは、<xref:System.Data.Linq.DataContext> およびエンティティ クラスのコードが生成される名前空間を決定します。 既定では、これらのプロパティは空であり、<xref:System.Data.Linq.DataContext> およびエンティティ クラスはアプリケーションの名前空間に生成されます。 アプリケーションの名前空間以外の名前空間にコードを生成するには、 **[Context Namespace]** プロパティ、 **[Entity Namespace]** プロパティ、またはその両方に値を入力します。

## <a name="reference-content"></a>参照コンテンツ

- <xref:System.Linq>
- <xref:System.Data.Linq>

## <a name="see-also"></a>関連項目

- [LINQ to SQL (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)
- [よく寄せられる質問 (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/frequently-asked-questions)