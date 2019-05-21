---
title: DataContext メソッド (O/R デザイナー) |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: c149f4e5-3b61-4c33-892e-3e26d47f3eeb
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2739fe3584080fd5dde185bde2ee1cefea844088
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65694018"
---
# <a name="datacontext-methods-or-designer"></a>DataContext メソッド (O/R デザイナー)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

DataContext] (assetId:///T:System.Data.Linq.DataContext?qualifyHint=False & autoUpgrade = True) メソッド (のコンテキストで、 [LINQ to SQL ツール Visual Studio で](../data-tools/linq-to-sql-tools-in-visual-studio2.md)) のメソッドは、<xref:System.Data.Linq.DataContext>ストアドを実行しているクラスプロシージャと、データベース内の関数。  
  
 <xref:System.Data.Linq.DataContext> クラスは、SQL Server データベースと、そのデータベースにマップされる [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] エンティティ クラスの間のパイプ役として機能する [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] クラスです。 <xref:System.Data.Linq.DataContext> クラスには、接続文字列の情報と、データベースへの接続およびデータベース内のデータの操作を行うメソッドが含まれています。 既定では、<xref:System.Data.Linq.DataContext> クラスには、更新されたデータを [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] クラスからデータベースに送信する <xref:System.Data.Linq.DataContext.SubmitChanges%2A> メソッドなど、呼び出すことのできるいくつかのメソッドがあります。 また、ストアド プロシージャおよび関数にマップされる追加の <xref:System.Data.Linq.DataContext> メソッドを作成することもできます。 つまり、これらのカスタム メソッドを呼び出すと、<xref:System.Data.Linq.DataContext> メソッドのマップ先となっているデータベース内のストアド プロシージャまたは関数が実行されます。 メソッドを追加して任意のクラスを拡張するのと同じように、<xref:System.Data.Linq.DataContext> クラスに新しいメソッドを追加できます。 ただし、に関するディスカッションで<xref:System.Data.Linq.DataContext>メソッドのコンテキストで、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]は、<xref:System.Data.Linq.DataContext>ストアド プロシージャとは、説明されている関数にマップされるメソッド。  
  
## <a name="methods-pane"></a>メソッド ペイン  
 ストアド プロシージャおよび関数にマップされる <xref:System.Data.Linq.DataContext> メソッドは、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]のメソッド ペインに表示されます。 メソッド ペインは、ウィンドウの横に、**エンティティ**ウィンドウ (メインのデザイン画面)。 メソッド ペインには、すべて一覧表示<xref:System.Data.Linq.DataContext>メソッドを使用して作成した、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]します。 既定では、メソッド ペインは空です。ストアド プロシージャまたは関数からのドラッグ**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**上に、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]を作成する<xref:System.Data.Linq.DataContext>メソッド メソッド ペインを設定します。 詳細については、「[方法 :ストアド プロシージャや関数にマップされる DataContext メソッドを作成する (O/R デザイナー)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)  
  
> [!NOTE]
> 右クリックし、メソッド ペインを開いたり閉じたり、 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]  をクリックし、**メソッド ペインの非表示に**または**メソッド ペインの表示**、またはキーボード ショートカット CTRL + 1 を使用します。  
  
## <a name="two-types-of-datacontext-methods"></a>2 種類の DataContext メソッド  
 DataContext メソッドは、データベース内のストアド プロシージャおよび関数にマップされるメソッドです。 DataContext メソッドは、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]のメソッド ペインで作成および追加できます。 <xref:System.Data.Linq.DataContext> メソッドには、1 つ以上の結果セットを返すものと結果セットを返さないものの 2 種類があります。  
  
- 1 つ以上の結果セットを返す <xref:System.Data.Linq.DataContext> メソッド  
  
     この種類の <xref:System.Data.Linq.DataContext> メソッドは、アプリケーションでデータベース内のストアド プロシージャおよび関数を実行し、結果を返すことだけが必要な場合に作成します。 詳細については、「[方法 :ストアド プロシージャおよび関数 (O/R デザイナー) にマップされる DataContext メソッドの作成](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)、System.Data.Linq.ISingleResult\<T >、および<xref:System.Data.Linq.IMultipleResults>します。  
  
- 結果セットを返さない <xref:System.Data.Linq.DataContext> メソッド (特定のエンティティ クラスの挿入、更新、削除など)  
  
     この種類の <xref:System.Data.Linq.DataContext> メソッドは、エンティティ クラスとデータベース間で変更されたデータを保存するために、既定の [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] の動作を使用するのではなく、アプリケーションでストアド プロシージャを実行する必要がある場合に作成します。 詳細については、「[方法 :更新、挿入、および削除を実行するストアド プロシージャを割り当てる (O/R デザイナー)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)」を参照してください。  
  
## <a name="return-types-of-datacontext-methods"></a>DataContext メソッドの戻り値の型  
 ストアド プロシージャおよび関数からのドラッグと**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**上に、 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]、戻り値の型を生成された<xref:System.Data.Linq.DataContext>メソッドとは異なる項目をドロップする場所によって異なります。 作成、既存のエンティティ クラスに直接の項目をドロップする、<xref:System.Data.Linq.DataContext>エンティティ クラスの戻り値の型を持つメソッドは項目をドロップの空の領域、 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] (いずれかのウィンドウ) では、作成、<xref:System.Data.Linq.DataContext>を返すメソッド、型が自動的に生成されます。 作成される自動生成の型は、ストアド プロシージャ名または関数名に一致する名前と、そのストアド プロシージャまたは関数によって返される各フィールドにマップされるプロパティを持ちます。  
  
> [!NOTE]
> <xref:System.Data.Linq.DataContext> メソッドをメソッド ペインに追加した後に、その戻り値の型を変更できます。 <xref:System.Data.Linq.DataContext> メソッドの戻り値の型を確認または変更するには、**[プロパティ]** ウィンドウでメソッドを選択し、**[戻り値の型]** プロパティを調べます。 詳細については、「[方法 :DataContext メソッドの戻り値の型を変更する (O/R デザイナー)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)」を参照してください。  
  
 データベースから O/R デザイナー画面にドラッグしたオブジェクトには、データベース内のオブジェクトの名前に基づいて自動的に名前が付けられます。 同じオブジェクトを複数回ドラッグすると、新しい名前の末尾に名前を区別する番号が付けられます。 データベース オブジェクト名にスペースや Visual Basic または C# でサポートされない文字が含まれている場合、そのスペースまたは無効な文字はアンダースコアに置き換えられます。  
  
## <a name="see-also"></a>関連項目  
 [LINQ to Visual Studio での SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [ストアド プロシージャ](https://msdn.microsoft.com/library/4d23dd7a-a85f-44ff-a717-af7d0950c0fc)   
 [方法: ストアド プロシージャおよび関数 (O/R デザイナー) にマップされる DataContext メソッドを作成します。](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)   
 [方法: 更新、挿入、および削除 (O/R デザイナー) を実行するストアド プロシージャを割り当てる](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)   
 [チュートリアル: 更新、およびエンティティ クラスの動作を削除、挿入をカスタマイズします。](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)   
 [チュートリアル: LINQ to SQL クラス (O/R デザイナー) を作成します。](https://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)
