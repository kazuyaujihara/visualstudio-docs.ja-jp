---
title: AddToCollection &lt;T &gt; アクティビティデザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.AddToCollection`1.UI
ms.assetid: f7fc0702-164e-4370-8946-bb2f9f9384b7
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 50deab447b3dcb93d352e73fc4765d913b4d24bf
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72659204"
---
# <a name="addtocollectionlttgt-activity-designer"></a>AddToCollection &lt;T &gt; アクティビティデザイナー
**Addtocollection \<T >** アクティビティデザイナーは、<xref:System.Activities.Statements.AddToCollection%601> アクティビティを作成および構成するために使用されます。

## <a name="the-addtocollectiont-activity"></a>AddToCollection \<T > アクティビティ
 <xref:System.Activities.Statements.AddToCollection%601> アクティビティでは、項目をコレクションに追加します。

### <a name="using-the-addtocollectiont-activity-designer"></a>AddToCollection \<T > アクティビティデザイナーの使用
 **Addtocollection \<T >** アクティビティデザイナーは、 **[ツールボックス]** の **[コレクション]** カテゴリにあります。このカテゴリにアクセスするには、[!INCLUDE[wfd2](../includes/wfd2-md.md)]**の [** **ツールボックス**] タブをクリックします。または、 **[表示]** メニューまたは CTRL + ALT + X)

 **Addtocollection \<T >** アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) [!INCLUDE[wfd2](../includes/wfd2-md.md)] にドロップできます。 これにより、AddToCollection \<Int32 > の既定の <xref:System.Activities.Activity.DisplayName%2A> を持つ <xref:System.Activities.Statements.AddToCollection%601> アクティビティが作成されます。 (既定では、 *Typeargument*は**Int32**です。 これは、プロパティグリッドで変更できます)。@No__t_0 値は、 **Addtocollection \<T >** アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。 他のプロパティは、プロパティ グリッドで編集する必要があります。

### <a name="the-addtocollectiont-properties"></a>AddToCollection \<T > プロパティ
 次の表に、<xref:System.Activities.Statements.AddToCollection%601> のプロパティと、デザイナーでのその使用方法を示します。

|プロパティ名|必要|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.AddToCollection%601> アクティビティの表示名。 既定値は、AddToCollection \<Int32 > です。 <xref:System.Activities.Activity.DisplayName%2A> 値は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.AddToCollection%601.Item%2A>|True|コレクションに追加する項目 \<T >。 この項目の型は*T*で、 *typeargument*型です。 項目を指定するには、プロパティ グリッドで Visual Basic の式を入力します。|
|<xref:System.Activities.Statements.AddToCollection%601.Collection%2A>|True|項目の追加先のコレクション。 このコレクションの型は**ICollection \<TypeArgument >** です。 コレクションを指定するには、プロパティ グリッドで Visual Basic の式を入力します。|
|*TypeArgument*|True|<xref:System.Collections.Generic.ICollection%601> に格納される項目の T 型。 既定では、この*Typeargument*型は**Int32**に設定されています。 型を変更するには、プロパティグリッドで、コンボボックスの*Typeargument*の値を変更します。|

## <a name="see-also"></a>参照
 [コレクション](../workflow-designer/collection-activity-designers.md) [addtocollection \<T > アクティビティデザイナー](../workflow-designer/addtocollection-t-activity-designer.md) [clearcollection \<T >](../workflow-designer/clearcollection-t-activity-designer.md)存在しない[コレクション \<T >](../workflow-designer/existsincollection-t-activity-designer.md) [removefromcollection \<T >](../workflow-designer/removefromcollection-t-activity-designer.md)