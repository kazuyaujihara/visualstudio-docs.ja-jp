---
title: '方法: LINQ to SQL クラス (O/R デザイナー) 間の関連付け (リレーションシップ) を作成する |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 56133e65-81f3-44c3-bc28-ffdd0671a0d2
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c5b97247ebf16a588e8f28b4b4e6f7c512566226
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63386773"
---
# <a name="how-to-create-an-association-relationship-between-linq-to-sql-classes-or-designer"></a>方法: LINQ to SQL クラス (O/R デザイナー) 間の関連付け (リレーションシップ) を作成します。
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] のエンティティ クラス間の関連付けは、データベース内のテーブル間の関連付けに似ています。 **[関連付けエディター]** ダイアログ ボックスを使用することで、エンティティ クラス間の関連付けを作成できます。  
  
 **[関連付けエディター]** ダイアログ ボックスを使用して関連付けを作成するときは、親クラスと子クラスを選択する必要があります。 親クラスは、主キーを含むエンティティ クラスであり、子クラスは、外部キーを含むエンティティ クラスです。 たとえば、Northwind の Customers テーブルと Orders テーブルにマップされるエンティティ クラスが作成された場合は、Customer クラスが親クラスであり、Order クラスが子クラスです。  
  
> [!NOTE]
> テーブルをドラッグすると**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**上に、 [!INCLUDE[vs_ordesigner_long](../includes/vs-ordesigner-long-md.md)] ([!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)])、アソシエーションが既存のに基づいて自動的に作成データベース内の外部キー リレーションシップ。  
  
 O/R デザイナーでアソシエーションを選択すると、アソシエーションを作成すると後、は、いくつかの構成可能なプロパティ、**プロパティ**ウィンドウ。 関連付けは、関連クラス間の線で表されます。次の表は、関連付けのプロパティの説明を示しています。  
  
|プロパティ|説明|  
|--------------|-----------------|  
|**カーディナリティ**|関連付けが 1 対多と 1 対 1 のどちらであるかを制御します。|  
|**子プロパティ**|コレクションのプロパティを親に作成するか、子レコードへの参照を関連付けの外部キー側に作成するかを指定します。 たとえば、Customer と Order 間の関連付けの場合、**子プロパティ**に設定されている**True**、Orders という名前のプロパティは、親クラスで作成されます。|  
|**親プロパティ**|関連付けられている親クラスを参照する子クラスのプロパティです。 たとえば、Customer と Order の間の関連付けでは、注文に関連付けられている顧客を参照する Customer という名前のプロパティが Order クラスに作成されます。|  
|**関与のプロパティ**|関連付けのプロパティを表示し、**[関連付けエディター]** ダイアログ ボックスを再び開く**省略記号**ボタン (...) が用意されています。|  
|**一意**|外部ターゲット列に一意性の制約があるかどうかを示します。|  
  
### <a name="to-create-an-association-between-entity-classes"></a>エンティティ クラス間に関連付けを作成するには  
  
1. 関連付けの親クラスを表すエンティティ クラスを右クリックし、**[追加]** をポイントして、**[関連付け]** をクリックします。  
  
2. **[関連付けエディター]** ダイアログ ボックスで、正しい**親クラス**が選択されていることを確認します。  
  
3. コンボ ボックスで**子クラス**を選択します。  
  
4. クラスに関連する **[関連付けのプロパティ]** を選択します。 通常、これはデータベースで定義されている外部キー リレーションシップにマップされます。 たとえば、顧客と注文の関連付けで、**関連付けのプロパティ**各クラスの CustomerID は。  
  
5. **[OK]** をクリックして、関連付けを作成します。  
  
## <a name="see-also"></a>関連項目  
 [LINQ to Visual Studio での SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [チュートリアル: LINQ to SQL クラス (O/R デザイナー) を作成します。](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [DataContext メソッド (O/R デザイナー)](../data-tools/datacontext-methods-o-r-designer.md)   
 [方法: 主キーを表す](http://msdn.microsoft.com/library/63c65289-6539-42b2-8493-891c232018fa)
