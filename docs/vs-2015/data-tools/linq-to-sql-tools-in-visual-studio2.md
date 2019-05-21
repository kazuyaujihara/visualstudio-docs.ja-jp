---
title: LINQ to SQL ツール |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 45e477c0-5c6b-41f9-b2d0-2808fb4f6537
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 24b874ab71cba23a3fe6cf4a6fb36293d6753935
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697769"
---
# <a name="linq-to-sql-tools-in-visual-studio"></a>LINQ to Visual Studio での SQL ツール
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

LINQ to SQL では、Microsoft によってリリースされた最初のオブジェクト リレーショナル マッピング テクノロジをしました。 基本的なシナリオに適していますし、引き続き Visual Studio でサポートされますが、アクティブな開発されていません。 LINQ to SQL、既に使用しているレガシ アプリケーションを保守する際に、または SQL Server を使用して、複数のテーブルのマッピングを必要としない単純なアプリケーションで使用します。 一般に、新しいアプリケーションは、オブジェクト リレーショナル マッパー層が必要な場合、Entity Framework を使用する必要があります。

 Visual Studio で、to SQL クラスを使用して SQL テーブルを表す LINQ を作成する、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]します。

 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]デザイン サーフェイスに 2 つの領域を持つ: エンティティ ペインで、左側と右側のメソッド ペインです。 エンティティ ペインは、エンティティ クラス、関連付け、および継承階層を表示するメインのデザイン サーフェイスです。 メソッド ペインは、ストアド プロシージャと関数にマッピングされる <xref:System.Data.Linq.DataContext> のメソッドを表示するデザイン サーフェイスです。

 [!INCLUDE[vs_ordesigner_long](../includes/vs-ordesigner-long-md.md)] ([!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]) を作成するためのビジュアル デ ザイン サーフェイスを提供します[LINQ to SQL](https://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)エンティティ クラスと、データベース内のオブジェクトに基づく関連付け (リレーションシップ)。 つまり、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]は、データベース内のオブジェクトにマップされるオブジェクト モデルをアプリケーションに作成するために使用されます。 また、エンティティ クラスとデータベース間でデータを送受信するために使用する、厳密に型指定された <xref:System.Data.Linq.DataContext> も生成します。 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]は、データを返し、エンティティ クラスを設定するために、ストアド プロシージャと関数を <xref:System.Data.Linq.DataContext> のメソッドにマップする機能も提供します。 最後に、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]では、エンティティ クラス間の継承関係をデザインすることもできます。

## <a name="opening-the-or-designer"></a>O/R デザイナーを開く
 LINQ to SQL エンティティのモデルをプロジェクトを追加する選択**プロジェクト&#124;新しい項目の追加**選び、 **LINQ to SQL クラス**プロジェクト項目の一覧から。

 ![LINQ to SQL クラス](../data-tools/media/raddata-linq-to-sql-classes.png "raddata LINQ to SQL クラス")

 Visual Studio では、.dbml ファイルを作成し、ソリューションに追加します。 これは、XML マッピング ファイルとその関連するコード ファイル。

 ![ソリューション エクスプ ローラーでの LINQ to SQL クラス](../data-tools/media/raddata-linq-to-sql-classes-in-solution-explorer.png "raddata LINQ to SQL は、ソリューション エクスプ ローラーでクラス")

 .Dbml ファイルを選択すると、Visual Studio には、視覚的にモデルを作成することができます、O/R デザイナー画面が表示されます。 次の図は、Northwind の Customers と Orders テーブルをサーバー エクスプ ローラーからドラッグされた後に、デザイナーを示します。 テーブル間のリレーションシップに注意してください。

 ![LINQ to SQL デザイナー](../data-tools/media/raddata-linq-to-sql-designer.png "raddata LINQ to SQL デザイナー")

> [!IMPORTANT]
> [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]簡単なオブジェクト リレーショナル マッパーは、1 対 1 のマッピング関係のみをサポートしているためです。 つまり、エンティティ クラスには、データベース テーブルまたはビューとの 1:1 のマッピング関係しか持たせることができません。 参加しているテーブルにエンティティ クラスのマッピングなどの複雑なマッピングはサポートされていません。複雑なマッピングの Entity Framework を使用します。 また、デザイナーは一方向のコード ジェネレーターです。 つまり、デザイナー サーフェイスに加えた変更だけがコード ファイルに反映されます。 コード ファイルに手動で加えた変更は、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]に反映されません。 コード ファイルに手動で加えた変更は、デザイナーを保存してコードを再生成するときに上書きされます。 ユーザー コードを追加し、によって生成されたクラスを拡張する方法については、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]を参照してください[方法。O/R デザイナーによって生成されたコードを拡張する](../data-tools/how-to-extend-code-generated-by-the-o-r-designer.md)します。

## <a name="creating-and-configuring-the-datacontext"></a>DataContext の作成と構成
 追加した後、 **LINQ to SQL クラス**項目プロジェクトを開き、 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]、空のデザイン サーフェイスは、空を表します<xref:System.Data.Linq.DataContext>構成可能になります。 <xref:System.Data.Linq.DataContext>デザイン サーフェイスにドラッグされる最初の項目によって提供される接続情報で構成されます. したがって、<xref:System.Data.Linq.DataContext> は、デザイン サーフェイスにドロップされた最初の項目の接続情報によって構成されます。 詳細については、<xref:System.Data.Linq.DataContext>クラス」を参照して[DataContext メソッド (O/R デザイナー)](../data-tools/datacontext-methods-o-r-designer.md)します。

## <a name="creating-entity-classes-that-map-to-database-tables-and-views"></a>データベース テーブルおよびビューにマップされるエンティティ クラスの作成
 データベース テーブルおよびビューからドラッグすることにより、テーブルとビューにマッピングされたエンティティ クラスを作成する**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**上に、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]します。 前のセクションで示したように、<xref:System.Data.Linq.DataContext> は、デザイン サーフェイスにドラッグされる最初の項目が提供する接続情報で構成されます。 別の接続を使用する項目が後で [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]に追加された場合は、<xref:System.Data.Linq.DataContext> の接続を変更できます。 詳細については、「[方法 :テーブルとビューにマップされた LINQ to SQL クラスを作成する (O/R デザイナー)](../data-tools/how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)」を参照してください。

## <a name="creating-datacontext-methods-that-call-stored-procedures-and-functions"></a>ストアド プロシージャおよび関数を呼び出す DataContext メソッドの作成
 作成することができます<xref:System.Data.Linq.DataContext>メソッドを呼び出す (にマップされる) ストアド プロシージャと関数をドラッグしてから**サーバー エクスプ ローラー**/**データベース エクスプ ローラー** に[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]. ストアド プロシージャと関数は、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]に <xref:System.Data.Linq.DataContext> のメソッドとして追加されます。

> [!NOTE]
> ストアド プロシージャおよび関数からのドラッグと**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**上に、 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]、戻り値の型を生成された<xref:System.Data.Linq.DataContext>メソッドとは異なる項目をドロップする場所によって異なります。 詳細については [DataContext メソッド (O/R デザイナー)](../data-tools/datacontext-methods-o-r-designer.md) を参照してください。

## <a name="configuring-a-datacontext-to-use-stored-procedures-to-save-data-between-entity-classes-and-a-database"></a>ストアド プロシージャを使用してエンティティ クラスとデータベース間でデータを保存するための DataContext の構成
 前に述べたように、ストアド プロシージャと関数を呼び出す <xref:System.Data.Linq.DataContext> のメソッドを作成できます。 また、挿入、更新、および削除を実行する既定の [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] ランタイムの動作の代わりに使用できる、ストアド プロシージャを割り当てることもできます。 詳細については、「[方法 :更新、挿入、および削除を実行するストアド プロシージャを割り当てる (O/R デザイナー)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)」を参照してください。

## <a name="inheritance-and-the-or-designer"></a>継承と O/R デザイナー
 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] クラスは、他のオブジェクトと同様に、継承を使用して他のクラスから派生できます。 データベースでは、継承関係が複数の方法で作成されます。 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]では、多くのリレーショナル システムに実装されている単一テーブル継承の概念がサポートされています。 詳細については、「[方法 :O/R デザイナーを使用して継承を構成する](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)」を参照してください。

## <a name="linq-to-sql-queries"></a>LINQ to SQL クエリ
 によって作成されたエンティティ クラス、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]で使用できるように設計された[LINQ (Language-Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)します。 詳細については、「[方法 :情報の照会](https://msdn.microsoft.com/library/e538d288-2070-40ca-9da6-4fbc68cd6ad0)します。

## <a name="separating-the-generated-datacontext-and-entity-class-code-into-different-namespaces"></a>生成された DataContext とエンティティ クラス コードの異なる名前空間への分離
 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]提供、**コンテキスト Namespace**と**Entity Namespace**プロパティを<xref:System.Data.Linq.DataContext>します。 これらのプロパティは、<xref:System.Data.Linq.DataContext> およびエンティティ クラスのコードが生成される名前空間を決定します。 既定では、これらのプロパティは空であり、<xref:System.Data.Linq.DataContext> およびエンティティ クラスはアプリケーションの名前空間に生成されます。 アプリケーションの名前空間以外の名前空間にコードを生成するには、**[Context Namespace]** プロパティ、**[Entity Namespace]** プロパティ、またはその両方に値を入力します。

## <a name="in-this-section"></a>このセクションの内容
 [DataContext メソッド (O/R デザイナー)](../data-tools/datacontext-methods-o-r-designer.md)内容について説明します<xref:System.Data.Linq.DataContext>メソッドと作成方法について説明します。

 [データ クラスの継承 (O/R デザイナー)](../data-tools/data-class-inheritance-o-r-designer.md)単一テーブル継承とでの実装方法の概念について説明します、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]します。

 [方法: LINQ to SQL クラスのテーブルとビュー (O/R デザイナー) にマップを作成](../data-tools/how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)テーブルおよびデータベースのビューにマップされるエンティティ クラスを作成する方法について説明します。

 [方法: LINQ to SQL クラス (O/R デザイナー) 間の関連付け (リレーションシップ) を作成する](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)間のリレーションシップを作成する方法について説明します[!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)]エンティティ クラスです。

 [方法: ストアド プロシージャおよび関数 (O/R デザイナー) にマップされる DataContext メソッドの作成](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)を作成する方法について説明します<xref:System.Data.Linq.DataContext>メソッドが呼び出されると、ストアド プロシージャまたは関数を実行しています。

 [方法: 更新、挿入、および削除 (O/R デザイナー) を実行するストアド プロシージャを割り当てる](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)を構成する方法について説明します、<xref:System.Data.Linq.DataContext>エンティティからデータを保存するときに、ストアド プロシージャを使用するクラスは、データベースをバックアップします。

 [方法: DataContext メソッド (O/R デザイナー) の戻り値の型を変更する](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)の戻り値の型を設定する方法について説明します、<xref:System.Data.Linq.DataContext>メソッドをエンティティ クラスの型または O/R デザイナーで作成された自動生成された型にします。

 [方法: 検証エンティティ クラスを追加する](../data-tools/how-to-add-validation-to-entity-classes.md)プロパティの変更とエンティティ クラスの更新中にコードを追加できるように部分メソッドを生成する方法について説明します。

 [方法: 複数形化のオンとオフにする (O/R デザイナー)](../data-tools/how-to-turn-pluralization-on-and-off-o-r-designer.md)オンとオフ、自動的に追加されるクラスの名前を変更する方法について説明します、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]します。

 [方法: O/R デザイナーを使用して継承を構成する](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)で単一テーブル継承を使用してエンティティ クラスを構成する方法について説明します、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]します。

 [方法: O/R デザイナーによって生成されたコードを拡張](../data-tools/how-to-extend-code-generated-by-the-o-r-designer.md)方法と場所について説明します、O/R デザイナー上のオブジェクトへの変更がコードを再生成時に上書きされないコードを追加します。

 [チュートリアル: LINQ to SQL クラスを使用して単一テーブル継承 (O/R デザイナー) を作成する](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)で単一テーブル継承を使用してエンティティ クラスを構成する手順について説明します、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]します。

 [チュートリアル: 更新、およびエンティティ クラスの動作を削除、挿入をカスタマイズするには、](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)を構成する手順について説明します、<xref:System.Data.Linq.DataContext>エンティティからデータを保存するときに、ストアド プロシージャを使用するクラスは、データベースをバックアップします。

## <a name="reference-content"></a>リファレンス コンテンツ
 <xref:System.Linq>

 <xref:System.Data.Linq>

## <a name="see-also"></a>関連項目
 [.NET 用の visual Studio データ ツール](../data-tools/visual-studio-data-tools-for-dotnet.md)[よく寄せられる質問](https://msdn.microsoft.com/library/252ed666-0679-4eea-b71b-2f14117ef443) [LINQ to SQL](https://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655) [Visual Studio でのデータにアクセスします。](../data-tools/accessing-data-in-visual-studio.md)
