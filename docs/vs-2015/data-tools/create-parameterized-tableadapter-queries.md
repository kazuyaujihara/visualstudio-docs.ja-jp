---
title: パラメーター付きの TableAdapter クエリを作成する
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- TableAdapters, parameterized queries
- data [Visual Studio], searching data
- queries [Visual Studio], creating
- TableAdapters, searching data
- queries [Visual Studio], TableAdapters
ms.assetid: 104d1d19-b5a9-4071-b81e-1b3af08e9c7b
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 49bc9f56a07319c9edad1522c5e44b0bb35e92a2
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58975884"
---
# <a name="create-parameterized-tableadapter-queries"></a>パラメーター付きの TableAdapter クエリを作成する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

パラメーター クエリは、クエリ内の WHERE 句の条件を満たすデータを返します。 たとえば、顧客リストをパラメーター化して、顧客のリストを戻す SQL ステートメントに `WHERE City = @City` を追加することで、特定の都市の顧客のみが表示されるようにできます。  
  
データセット デザイナーでは、パラメーター化された TableAdapter クエリを作成します。 Windows アプリケーションで作成することも、**データ ソースのパラメーター化**コマンドを**データ**メニュー。 **データ ソースのパラメーター化**コマンドは、パラメーター値を入力して、クエリを実行できますフォーム上のコントロールを作成します。  
  
> [!NOTE]
> パラメーター化クエリを構築するときに、に対してコーディングをしているデータベースに固有のパラメーター表記を使用します。 たとえば、Access データ ソースと OleDb データ ソースは疑問符 "?" を使用してパラメーターを表すため、WHERE 句は `WHERE City = ?` のようになります。  
  
> [!NOTE]
> アクティブな設定または使用しているエディションによって、ヘルプの記載されているダイアログ ボックスとメニュー コマンドが表示が異なる場合があります。 設定を変更するには、**ツール**メニュー選択し、**インポートおよびエクスポート設定**します。 詳細については、「 [Visual Studio での開発設定のカスタマイズ](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
## <a name="create-a-parameterized-tableadapter-query"></a>パラメーター化された TableAdapter クエリを作成します。 
  
- 新しい TableAdapter を作成し、目的のパラメーターを含む WHERE 句を SQL ステートメントに追加します。 詳細については、次を参照してください。[作成し、Tableadapter 構成](../data-tools/create-and-configure-tableadapters.md)します。  
  
     - または -  
  
- 既存の TableAdapter にクエリを追加し、目的のパラメーターを含む WHERE 句を SQL ステートメントに追加します。
  
### <a name="create-a-parameterized-query-while-designing-a-data-bound-form"></a>データ バインド フォームのデザイン時にパラメーター化クエリを作成します。  
  
1.  フォーム上の既にデータセットにバインドされているコントロールを選択します。 詳細については、次を参照してください。 [Visual Studio でのデータにコントロールを Windows フォームのバインド](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)します。  
  
2.  **データ**メニューの **クエリの追加**します。  
  
3.  **[検索条件ビルダー]** ダイアログ ボックスの設定を完了し、目的のパラメーターを含む WHERE 句を SQL ステートメントに追加します。  
  
### <a name="add-a-query-to-an-existing-data-bound-form"></a>クエリを既存のデータ バインド フォームに追加します。  
  
1. **Windows フォーム デザイナー**でフォームを開きます。  
  
2. **データ**メニューの **クエリの追加**または**データ スマート タグ**します。  
  
   > [!NOTE]
   > **[データ]** メニューの **[クエリの追加]** が使用できない場合は、パラメーターの追加先のデータ ソースを表示するフォーム上のコントロールを選択します。 たとえば、フォームに <xref:System.Windows.Forms.DataGridView> コントロールのデータが表示される場合は、そのコントロールを選択します。 フォームに個々のコントロールのデータが表示される場合は、いずれかのデータ バインド コントロールを選択します。  
  
3. **ソース テーブルのデータの選択**領域で、追加するパラメーター化を選択 tablethat します。  
  
4. 新しいクエリを作成する場合は、**[新しいクエリ名]** ボックスに名前を入力します。  
  
    - または -  
  
    **[既存のクエリ名]** ボックスでクエリを選択します。  
  
5. **クエリ テキスト**ボックスに、パラメーターを受け取るクエリを入力します。  
  
6. **[OK]** を選択します。  
  
    パラメーターを入力するコントロールと **[読み込み]** ボタンが、<xref:System.Windows.Forms.ToolStrip> コントロールのフォームに追加されます。  
  
   現在の値を持たないレコードを照会するときに、TableAdapter のパラメーターが null 値を割り当てることできます。 たとえば、次のクエリを持つ、`ShippedDate`パラメーターでその`WHERE`句。  
  
   ```sql
   SELECT CustomerID, OrderDate, ShippedDate  
   FROM Orders  
   WHERE (ShippedDate = @ShippedDate) OR  
   (ShippedDate IS NULL)  
   ```

これは TableAdapter 上のクエリの場合、次のコードにまだ配送されていないすべての注文のクエリを実行でした。  
  
   [!code-csharp[VbRaddataTableAdapters#8](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataTableAdapters/CS/Form2.cs#8)]
   [!code-vb[VbRaddataTableAdapters#8](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataTableAdapters/VB/Form2.vb#8)]  
  
### <a name="enable-a-query-to-accept-null-values"></a>Null 値を使用するためのクエリを有効にします。  
  
1.  **データセット デザイナー**、null パラメーター値をそのまま使用する必要がある TableAdapter クエリを選択します。  
  
2.  **プロパティ**ウィンドウで、**パラメーター**します。 省略記号ボタンを押します (**.**) ボタンをクリックする、**パラメーター コレクション エディター**します。  
  
3.  Null 値を許容するパラメーターを選択し、設定、 **AllowDbNull**プロパティを`true`します。  
  
## <a name="see-also"></a>関連項目

- [TableAdapters を使用してデータセットを入力する](../data-tools/fill-datasets-by-using-tableadapters.md)