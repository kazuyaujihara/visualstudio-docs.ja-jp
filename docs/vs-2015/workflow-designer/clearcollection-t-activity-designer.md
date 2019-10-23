---
title: ClearCollection &lt;T &gt; アクティビティデザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ClearCollection`1.UI
ms.assetid: db0e5da2-7b5a-4f1a-864c-f3aeeeeb51a7
caps.latest.revision: 7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 8c2f1e0264d39c65601a70e8c24b51c7eceadf4a
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72657016"
---
# <a name="clearcollectionlttgt-activity-designer"></a>ClearCollection &lt;T &gt; アクティビティデザイナー
@No__t_2 アクティビティを作成および構成するには、 **Clearcollection \<T >** アクティビティデザイナーを使用します。

## <a name="the-clearcollectiont-activity"></a>ClearCollection \<T > アクティビティ
 <xref:System.Activities.Statements.ClearCollection%601> アクティビティで、指定したすべての項目のコレクションをクリアします。

### <a name="using-the-clearcollectiont-activity-designer"></a>ClearCollection \<T > アクティビティデザイナーの使用
 **Clearcollection \<T >** アクティビティデザイナーは、**ツールボックス**の **[コレクション]** カテゴリにあります。このカテゴリにアクセスするには、[!INCLUDE[wfd2](../includes/wfd2-md.md)]**の [** **ツールボックス**] タブをクリックします。または、 **[表示]** メニューまたは CTRL + ALT + X)

 **Clearcollection \<T >** アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) [!INCLUDE[wfd2](../includes/wfd2-md.md)] にドロップできます。 これにより、ClearCollection \<Int32 > の既定の <xref:System.Activities.Activity.DisplayName%2A> を持つ <xref:System.Activities.Statements.ClearCollection%601> アクティビティが作成されます。 (既定では、 *Typeargument*は**Int32**です。 これは、プロパティグリッドで変更できます)。@No__t_0 値は、 **Clearcollection \<T >** アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。 他のプロパティは、プロパティ グリッドで編集する必要があります。

### <a name="the-clearcollectiont-properties"></a>ClearCollection \<T > プロパティ
 次の表に、<xref:System.Activities.Statements.ClearCollection%601> のプロパティと、デザイナーでのその使用方法を示します。

|プロパティ名|必要|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.ClearCollection%601> アクティビティの表示名を指定します (省略可能)。 既定値は ClearCollection \<Int32 > です。 <xref:System.Activities.Activity.DisplayName%2A> 値は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.ClearCollection%601.Collection%2A>|True|クリアする項目のコレクションを指定します。 このコレクションの型は**ICollection \<TypeArgument > です。** コレクションを指定するには、プロパティ グリッドで Visual Basic の式を入力します。|
|*TypeArgument*|True|<xref:System.Collections.Generic.ICollection%601> に格納される項目の T 型を指定します。 既定では、この*Typeargument*型は**Int32**に設定されています。 型を変更するには、プロパティグリッドで、コンボボックスの*Typeargument*の値を変更します。|

## <a name="see-also"></a>参照
 [コレクション](../workflow-designer/collection-activity-designers.md) [addtocollection \<T >](../workflow-designer/addtocollection-t-activity-designer.md)存在しないコレクション[\<T >](../workflow-designer/existsincollection-t-activity-designer.md) [removefromcollection \<T >](../workflow-designer/removefromcollection-t-activity-designer.md)