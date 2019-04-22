---
title: 1 つ以上の DataContext メソッドの戻り値の型として使用されるため、選択したクラスを削除できません。Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 02454e308a97f043caa6e85e1c4308c2d2a2402e
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59649044"
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>選択したクラスは、1 つ以上の DataContext メソッドで戻り値の型として使用されているため、削除できません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

1 つ以上の <xref:System.Data.Linq.DataContext> メソッドの戻り値の型が、選択されたエンティティ クラスになっています。 <xref:System.Data.Linq.DataContext> メソッドの戻り値の型として使用されているエンティティ クラスを削除すると、プロジェクトのコンパイルに失敗する原因となります。 選択したエンティティ クラスを削除するには、そのエンティティ クラスを使用する <xref:System.Data.Linq.DataContext> メソッドを特定し、戻り値の型を別のエンティティ クラスに設定します。  
  
 戻り値の型を元に戻す<xref:System.Data.Linq.DataContext>最初に削除する元自動生成された型をメソッド、<xref:System.Data.Linq.DataContext>メソッド ペインからメソッドからオブジェクトをドラッグして**サーバー エクスプ ローラー** / **データベース エクスプ ローラー**もう一度 O/R デザイナーにします。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  識別<xref:System.Data.Linq.DataContext>エンティティ クラスを選択して戻り値の型として使用するメソッド、<xref:System.Data.Linq.DataContext>メソッドにメソッド ペインおよび検査、**戻り値の型**プロパティ、**プロパティ**ウィンドウ.  
  
2.  **[戻り値の型]** を別のエンティティ クラスに設定するか、メソッド ペインから <xref:System.Data.Linq.DataContext> メソッドを削除します。  
  
## <a name="see-also"></a>関連項目  
 [LINQ to Visual Studio での SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [チュートリアル: LINQ to SQL クラス (O/R デザイナー) を作成します。](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [DataContext メソッド (O/R デザイナー)](../data-tools/datacontext-methods-o-r-designer.md)   
 [方法: DataContext メソッドの戻り値の型を変更する (O/R デザイナー)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)
