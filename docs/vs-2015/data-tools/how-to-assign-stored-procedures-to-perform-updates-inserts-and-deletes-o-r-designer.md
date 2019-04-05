---
title: '方法: 更新、挿入、および削除 (O/R デザイナー) を実行するストアド プロシージャを割り当てる |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: e88224ab-ff61-4a3a-b6b8-6f3694546cac
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 957c1fe49d222a691160eadc4b2cf08f8a20a65a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58975296"
---
# <a name="how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-or-designer"></a>方法: 更新、挿入、および削除を実行するストアド プロシージャを割り当てる (O/R デザイナー)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
ストアド プロシージャは O/R デザイナーに追加でき、通常の <xref:System.Data.Linq.DataContext> メソッドとして実行できます。 既定値も使用[!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)]実行時の動作を挿入、更新を実行し、データベースに、エンティティ クラスから変更が保存されたときに削除します (などを呼び出すときに、<xref:System.Data.Linq.DataContext.SubmitChanges%2A>メソッド)。  
  
> [!NOTE]
>  ストアド プロシージャが、クライアントに送信する必要のある値 (たとえば、ストアド プロシージャで計算された値) を返す場合は、ストアド プロシージャに出力パラメーターを作成します。 出力パラメーターを使用できない場合は、O/R デザイナーによって生成されたオーバーライドを利用するのではなく、部分メソッドを実装します。 データベースによって生成される値にマップされるメンバーは、INSERT 操作または UPDATE 操作が正常に完了した後で、適切な値に設定する必要があります。 詳細については、次を参照してください。[開発者でオーバーライドする既定の動作の責任](http://msdn.microsoft.com/library/c6909ddd-e053-46a8-980c-0e12a9797be1)します。  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] は、ID 列 (自動インクリメント)、rowguidcol 列 (データベースが生成した GUID)、およびタイムスタンプ列であれば、データベースによって生成された値を自動的に処理します。 その他の列型のデータベースが生成した値は、予想に反して null 値になります。 データベースが生成した値を返すには、手動で <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> を `true` に設定し、<xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A> を <xref:System.Data.Linq.Mapping.AutoSync>、<xref:System.Data.Linq.Mapping.AutoSync>、または <xref:System.Data.Linq.Mapping.AutoSync> のいずれかに設定する必要があります。  
  
## <a name="configuring-the-update-behavior-of-an-entity-class"></a>エンティティ クラスの更新動作の構成  
 既定では、[!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] エンティティ クラスのデータに対して行われた変更でデータベースを更新 (挿入、更新、および削除) するロジックは、[!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] ランタイムによって提供されます。 ランタイムは、既定値 (列と主キー情報) のテーブルのスキーマに基づく Insert、Update、および Delete コマンドを作成します。 既定の動作が望ましくないと、更新動作を構成するには、必要な挿入、更新を実行するための特定のストアド プロシージャを割り当てることで、テーブルのデータを操作するために必要な削除。 この方法は、既定の動作が生成されていない場合、たとえばエンティティ クラスがビューにマップされている場合にも実行できます。 最後に、データベースのテーブルへのアクセスには常にストアド プロシージャを通すようにすると、既定の更新動作をオーバーライドできます。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
#### <a name="to-assign-stored-procedures-to-override-the-default-behavior-of-an-entity-class"></a>ストアド プロシージャを割り当てて、エンティティ クラスの既定の動作をオーバーライドするには  
  
1.  デザイナーで **LINQ to SQL** ファイルを開きます。 (で .dbml ファイルをダブルクリック**ソリューション エクスプ ローラー**)。  
  
2.  **サーバー エクスプ ローラー**/**データベース エクスプ ローラー**、展開**Stored Procedures** Insert、Update を使用するストアド プロシージャを探しますまたは、エンティティ クラスのコマンドを削除します。  
  
3.  ストアド プロシージャを O/R デザイナーにドラッグします。  
  
     ストアド プロシージャが <xref:System.Data.Linq.DataContext> メソッドとしてメソッド ペインに追加されます。 詳細については [DataContext メソッド (O/R デザイナー)](../data-tools/datacontext-methods-o-r-designer.md) を参照してください。  
  
4.  更新の実行にストアド プロシージャを使用するエンティティ クラスを選択します。  
  
5.  **[プロパティ]** ウィンドウで、オーバーライドするコマンド (**[Insert]**、**[Update]**、または **[Delete]**) を選択します。  
  
6.  **[ランタイムを使用]** の横にある省略記号 ([...]) をクリックして、**[動作の構成]** ダイアログ ボックスを開きます。  
  
7.  **[カスタマイズ]** を選択します。  
  
8.  **[カスタマイズ]** リストで、目的のストアド プロシージャを選択します。  
  
9. **[メソッドの引数]** および **[クラスのプロパティ]** のリストを調べて、**[メソッドの引数]** が適切な **[クラスのプロパティ]** にマップされていることを確認します。 マップ元のメソッド引数 (original _*ArgumentName*) を元のプロパティ (*PropertyName* (オリジナル)) の Update および Delete コマンド。  
  
    > [!NOTE]
    >  既定では、メソッド引数は名前が一致した場合にクラス プロパティにマップされます。 変更されたプロパティ名がテーブルとエンティティ クラス間で一致しなくなり、デザイナーが正しいマッピングを判断できないときは、マップ先となる同等のクラス プロパティを選択することが必要になる場合があります。  
  
10. **[OK]** または **[適用]** をクリックします。  
  
    > [!NOTE]
    >  変更を行うたびに **[適用]** をクリックすると、各クラスと動作の組み合わせに対して動作の構成を続けることができます。 クリックする前に、クラスまたは動作を変更するかどうかは**適用**、警告ダイアログ ボックスを提供するすべての変更を適用する機会が表示されます。  
  
     既定のランタイム ロジックを使用して、更新に戻すには、Insert、Update、横にある省略記号をクリックしてまたは Delete コマンドで、**プロパティ**クリックしてウィンドウ**ランタイムを使用して、** で、 **動作を構成する** ダイアログ ボックス。  
  
## <a name="see-also"></a>関連項目  
 [LINQ to Visual Studio での SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [DataContext メソッド (O/R デザイナー)](../data-tools/datacontext-methods-o-r-designer.md)   
 [チュートリアル: LINQ to SQL クラス (O/R デザイナー) を作成します。](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [挿入、更新、および削除の各操作](http://msdn.microsoft.com/library/26a43a4f-83c9-4732-806d-bb23aad0ff6b)
