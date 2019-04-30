---
title: '方法: ストアド プロシージャおよび関数 (O/R デザイナー) にマップされる DataContext メソッドの作成 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: e7ca32f1-50b3-48af-ad92-ceafd749296a
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 33791123681cc16f3568416e38b27e689324cf0d
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63386189"
---
# <a name="how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-or-designer"></a>方法: ストアド プロシージャや関数にマップされる DataContext メソッドを作成する (O/R デザイナー)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ストアド プロシージャおよび関数に追加できる、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]として<xref:System.Data.Linq.DataContext>メソッド。 メソッドを呼び出して必要なパラメーターを渡すと、データベースでストアド プロシージャまたは関数が実行され、<xref:System.Data.Linq.DataContext> メソッドの戻り値の型のデータが返されます。 詳細については<xref:System.Data.Linq.DataContext>メソッドを参照してください[DataContext メソッド (O/R デザイナー)](../data-tools/datacontext-methods-o-r-designer.md)します。  
  
> [!NOTE]
> ストアド プロシージャを使用して、エンティティ クラスからデータベースに変更が保存されたときに挿入、更新、および削除を実行する既定の [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] ランタイムの動作をオーバーライドすることもできます。 詳細については、「[方法 :更新、挿入、および削除を実行するストアド プロシージャを割り当てる (O/R デザイナー)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)」を参照してください。  
  
## <a name="creating-datacontext-methods"></a>DataContext メソッドの作成  
 作成することができます<xref:System.Data.Linq.DataContext>メソッドをドラッグしてストアド プロシージャまたは関数から**サーバー エクスプ ローラー/データベース エクスプ ローラー**上に、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]します。  
  
> [!NOTE]
> 生成される <xref:System.Data.Linq.DataContext> メソッドの戻り値の型は、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]でストアド プロシージャまたは関数をドロップする場所によって異なります。 既存のエンティティ クラスに項目を直接ドロップすると、そのエンティティ クラスを戻り値の型とする <xref:System.Data.Linq.DataContext> メソッドが作成されます。 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]の空の領域に項目をドロップすると、自動生成された型を返す <xref:System.Data.Linq.DataContext> メソッドが作成されます。 戻り値の型を変更することができます、<xref:System.Data.Linq.DataContext>メソッド ペインに追加したメソッド。 <xref:System.Data.Linq.DataContext> メソッドの戻り値の型を確認または変更するには、**[プロパティ]** ウィンドウでメソッドを選択し、**[戻り値の型]** プロパティを調べます。 詳細については、「[方法 :DataContext メソッドの戻り値の型を変更する (O/R デザイナー)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)」を参照してください。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
#### <a name="to-create-datacontext-methods-that-return-automatically-generated-types"></a>自動生成された型を返す DataContext メソッドを作成するには  
  
1. **サーバー エクスプ ローラー**/**データベース エクスプ ローラー**、展開、 **Stored Procedures**を使用するデータベースのノード。  
  
2. 目的のストアド プロシージャを探し、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]の空の領域にドラッグします。  
  
     自動生成された戻り値の型を使用して <xref:System.Data.Linq.DataContext> メソッドが作成され、**[メソッド]** ペインに表示されます。  
  
#### <a name="to-create-datacontext-methods-that-have-the-return-type-of-an-entity-class"></a>エンティティ クラスを戻り値の型とする DataContext メソッドを作成するには  
  
1. **サーバー エクスプ ローラー**/**データベース エクスプ ローラー**、展開、 **Stored Procedures**を使用するデータベースのノード。  
  
2. 目的のストアド プロシージャを探し、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]の既存のエンティティ クラスにドラッグします。  
  
     選択したエンティティ クラスを戻り値の型として <xref:System.Data.Linq.DataContext> メソッドが作成され、**[メソッド]** ペインに表示されます。  
  
> [!NOTE]
> 既存の戻り値の型を変更する方法について<xref:System.Data.Linq.DataContext>メソッドを参照してください[方法。DataContext メソッドの戻り値の型を変更する (O/R デザイナー)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [LINQ to Visual Studio での SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [DataContext メソッド (O/R デザイナー)](../data-tools/datacontext-methods-o-r-designer.md)   
 [チュートリアル: LINQ to SQL クラス (O/R デザイナー) を作成します。](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [Visual Basic における LINQ の概要](http://msdn.microsoft.com/library/3047d86e-0d49-40e2-928b-dc02e46c7984)   
 [方法: C# で LINQ クエリを作成します。](http://msdn.microsoft.com/library/45e47fcc-cfa1-4b72-b161-d038ae87bd23)
