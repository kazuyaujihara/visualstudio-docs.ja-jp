---
title: 関連付けを作成できません&lt;アソシエーション名&gt;-プロパティが 2 回一覧表示 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 3ced8bda-210e-4caf-9d8f-96cdbba19251
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b9592605a25c76b4ea17b6efe91363d59585f56e
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59660971"
---
# <a name="cannot-create-an-association-ltassociation-namegt---property-listed-twice"></a>関連付け &lt;関連付けの名前&gt; を作成できません - プロパティが 2 回リストされています
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

関連付け \<関連付けの名前> を作成できません。 同じプロパティが複数リストされています: "\<property name>"。  
  
 関連付けは、**[関連付けエディター]** ダイアログ ボックスで選択された **[関連付けのプロパティ]** によって定義されます。 プロパティは、関連付けのクラスごとに 1 回のみリストできます。  
  
 メッセージに示されているプロパティは、Parent クラスまたは Child クラスの **[関連付けのプロパティ]** に複数回表示されます。  
  
### <a name="to-resolve-this-condition"></a>この状況の解決方法  
  
-   メッセージを確認し、メッセージで指定されているプロパティに注目します。  
  
-   **[OK]** をクリックしてメッセージ ボックスを閉じます。  
  
-   **[関連付けのプロパティ]** を調べて、重複エントリを削除します。  
  
-   **[OK]** をクリックします。  
  
## <a name="see-also"></a>関連項目  
 [LINQ to Visual Studio での SQL ツール](http://msdn.microsoft.com/library/a57e82d5-f7e4-4894-8add-3d9ba4fce186)   
 [方法: LINQ to SQL クラス (O/R デザイナー) 間の関連付け (リレーションシップ) を作成します。](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)   
 [チュートリアル: LINQ to SQL クラス (O/R デザイナー) を作成します。](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)
