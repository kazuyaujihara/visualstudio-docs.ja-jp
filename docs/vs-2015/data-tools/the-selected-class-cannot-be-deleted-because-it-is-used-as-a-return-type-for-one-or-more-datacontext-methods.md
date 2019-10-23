---
title: 選択したクラスは、1つまたは複数の DataContext メソッドの戻り値の型として使用されているため、削除できません |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
caps.latest.revision: 8
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: cf16fe7453388e19308ed603ee9dbbac207cec41
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72667258"
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>選択したクラスは、1 つ以上の DataContext メソッドで戻り値の型として使用されているため、削除できません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

1 つ以上の <xref:System.Data.Linq.DataContext> メソッドの戻り値の型が、選択されたエンティティ クラスになっています。 <xref:System.Data.Linq.DataContext> メソッドの戻り値の型として使用されているエンティティ クラスを削除すると、プロジェクトのコンパイルに失敗する原因となります。 選択したエンティティ クラスを削除するには、そのエンティティ クラスを使用する <xref:System.Data.Linq.DataContext> メソッドを特定し、戻り値の型を別のエンティティ クラスに設定します。

 @No__t_0 メソッドの戻り値の型を元の自動生成型に戻すには、最初にメソッドペインから <xref:System.Data.Linq.DataContext> メソッドを削除してから、オブジェクトを**サーバーエクスプローラー** / の**データベースエクスプローラー**から O/R デザイナーにもう一度ドラッグします。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. [メソッド] ペインで <xref:System.Data.Linq.DataContext> メソッドを選択し、 **[プロパティ]** ウィンドウで **[戻り値の型]** プロパティを調べることによって、エンティティクラスを戻り値の型として使用する <xref:System.Data.Linq.DataContext> メソッドを識別します。

2. **[戻り値の型]** を別のエンティティ クラスに設定するか、メソッド ペインから <xref:System.Data.Linq.DataContext> メソッドを削除します。

## <a name="see-also"></a>参照
 [Visual Studio の LINQ to SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)[チュートリアル: LINQ to SQL クラスの作成 (o](https://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233) /r デザイナー) [Datacontext メソッド (o/r デザイナー)](../data-tools/datacontext-methods-o-r-designer.md) [方法: DataContext メソッドの戻り値の型を変更する (o/r デザイナー)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)
