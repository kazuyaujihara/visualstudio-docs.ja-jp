---
title: プロパティ&lt;プロパティ名&gt;関連付けに関与しているために削除できません&lt;アソシエーション名&gt;|Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: a3ba746f9e4dcd8da45a002c5c763384558342ec
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60053911"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>プロパティ &lt;プロパティ名&gt; は関連付け &lt;関連付けの名前&gt; に関与しているため、削除できません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

選択されたプロパティは、エラー メッセージに示されているクラス間の関連付けに対する**関連付けプロパティ**として設定されています。 プロパティがデータ クラス間の関連付けに関与している場合、そのプロパティを削除することはできません。  
  
 **関連付けプロパティ**をデータ クラスの別のプロパティに設定して、目的のプロパティが正常に削除されるようにします。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1. O/R デザイナーで、エラー メッセージに示されているデータ クラスを接続する関連行を選択します。  
  
2. 行をダブルクリックして、**[関連付けエディター]** ダイアログ ボックスを開きます。  
  
3. **[関連付けのプロパティ]** からプロパティを削除します。  
  
4. プロパティの削除を再試行します。  
  
## <a name="see-also"></a>関連項目  
 [LINQ to Visual Studio での SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [方法: LINQ to SQL クラス (O/R デザイナー) 間の関連付け (リレーションシップ) を作成します。](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)   
 [チュートリアル: LINQ to SQL クラス (O/R デザイナー) を作成します。](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)
