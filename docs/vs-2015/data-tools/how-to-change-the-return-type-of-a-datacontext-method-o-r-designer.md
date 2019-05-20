---
title: '方法: DataContext メソッド (O/R デザイナー) の戻り値の型の変更 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: c5b66bff-6dbb-43c0-bffa-317133ca5b9e
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: dd954761bdac5d453cb21331513cf92df9d415c7
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65684752"
---
# <a name="how-to-change-the-return-type-of-a-datacontext-method-or-designer"></a>方法: DataContext メソッドの戻り値の型を変更する (O/R デザイナー)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ストアド プロシージャまたは関数に基づいて作成された <xref:System.Data.Linq.DataContext> メソッドの戻り値の型は、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]でストアド プロシージャまたは関数をドロップした場所に応じて異なります。 既存のエンティティ クラスに項目を直接ドロップすると、そのエンティティ クラスを戻り値の型とする <xref:System.Data.Linq.DataContext> メソッドが作成されます (ストアド プロシージャまたは関数によって返されるデータのスキーマがエンティティ クラスの形状と一致する場合)。 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]の空の領域に項目をドロップすると、自動生成された型を返す <xref:System.Data.Linq.DataContext> メソッドが作成されます。 <xref:System.Data.Linq.DataContext> メソッドをメソッド ペインに追加した後に、その戻り値の型を変更できます。 <xref:System.Data.Linq.DataContext> メソッドの戻り値の型を確認または変更するには、**[プロパティ]** ウィンドウでメソッドを選択し、**[戻り値の型]** プロパティをクリックします。  
  
> [!NOTE]
> **[プロパティ]** ウィンドウを使用しても、戻り値の型がエンティティ クラスに設定されている <xref:System.Data.Linq.DataContext> メソッドは、自動生成型を返すようには変更できません。 自動生成型を返すように <xref:System.Data.Linq.DataContext> メソッドを戻すには、元のデータベース オブジェクトをもう一度 O/R デザイナーにドラッグする必要があります。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-change-the-return-type-of-a-datacontext-method-from-the-auto-generated-type-to-an-entity-class"></a>DataContext メソッドの戻り値の型を、自動生成型からエンティティ クラスに変更するには  
  
1. メソッド ペインで <xref:System.Data.Linq.DataContext> メソッドを選択します。  
  
2. **[プロパティ]** ウィンドウの **[戻り値の型]** を選択し、**[戻り値の型]** リストで使用可能なエンティティ クラスを選択します。 一覧で目的のエンティティ クラスでない場合にそれを追加または作成、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]一覧に追加します。  
  
3. .dbml ファイルを保存します。  
  
### <a name="to-change-the-return-type-of-a-datacontext-method-from-an-entity-class-back-to-the-auto-generated-type"></a>DataContext メソッドの戻り値の型を、エンティティ クラスから自動生成型に変更するには  
  
1. メソッド ペインで <xref:System.Data.Linq.DataContext> メソッドを選択し、削除します。  
  
2. データベース オブジェクトをドラッグして**サーバー エクスプ ローラー**/**データベース エクスプ ローラー** O/R デザイナーの空の領域にします。  
  
3. .dbml ファイルを保存します。  
  
## <a name="see-also"></a>関連項目  
 [LINQ to Visual Studio での SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [DataContext メソッド (O/R デザイナー)](../data-tools/datacontext-methods-o-r-designer.md)   
 [方法: ストアド プロシージャや関数にマップされる DataContext メソッドを作成する (O/R デザイナー)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)
