---
title: RemoveFromCollection &lt;T &gt; アクティビティデザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.RemoveFromCollection`1.UI
ms.assetid: 6617ba26-c8bc-4aed-b746-112bf490d288
caps.latest.revision: 6
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3ac088c6e5710fcd1b7c401402ad473488f89524
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672575"
---
# <a name="removefromcollectionlttgt-activity-designer"></a>RemoveFromCollection &lt;T &gt; アクティビティデザイナー
@No__t_2 アクティビティを作成および構成するには、 **Removefromcollection \<T >** アクティビティデザイナーを使用します。

## <a name="the-removefromcollectiont-activity"></a>RemoveFromCollection \<T > アクティビティ
 <xref:System.Activities.Statements.RemoveFromCollection%601> アクティビティは、指定した項目を特定のコレクションから削除します。

### <a name="using-the-removefromcollectiont-activity-designer"></a>RemoveFromCollection \<T > アクティビティデザイナーの使用
 **Removefromcollection \<T >** アクティビティデザイナーは、**ツールボックス**の **[コレクション]** カテゴリにあります。このカテゴリにアクセスするには、[!INCLUDE[wfd2](../includes/wfd2-md.md)] の **[ツールボックス]** タブをクリックします (または、 **[ツールバー]** を選択します)。 **[表示]** メニュー、または CTRL + ALT + X キー)

 **Removefromcollection \<T >** アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) [!INCLUDE[wfd2](../includes/wfd2-md.md)] にドロップできます。 これにより、RemoveFromCollection \<Int32 > の既定の <xref:System.Activities.Activity.DisplayName%2A> を持つ <xref:System.Activities.Statements.RemoveFromCollection%601> アクティビティが作成されます。 @No__t_0 値は、 **Removefromcollection \<T >** アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。 他のプロパティは、プロパティ グリッドで編集する必要があります。

### <a name="the-removefromcollectiont-properties"></a>RemoveFromCollection \<T > プロパティ
 次の表に、<xref:System.Activities.Statements.RemoveFromCollection%601> のプロパティと、デザイナーでのその使用方法を示します。

|プロパティ名|必要|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.RemoveFromCollection%601> アクティビティの省略可能な表示名。 既定値は、RemoveFromCollection \<Int32 > です。<br /><br /> <xref:System.Activities.Activity.DisplayName%2A> は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Item%2A>|True|コレクションに追加する項目 **\<T >** 。 この項目の型は*T*で、 *typeargument*型です。 項目を指定するには、プロパティ グリッドで Visual Basic の式を入力します。|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Collection%2A>|True|項目の追加先のコレクション。 このコレクションの型は**ICollection \<TypeArgument > です。** コレクションを指定するには、プロパティグリッドで Visual Basic 式を入力します。|
|*TypeArgument*|True|<xref:System.Collections.Generic.ICollection%601> に格納される項目の T 型。 既定では、この*Typeargument*型は**Int32**に設定されています。 型を変更するには、プロパティグリッドで、コンボボックスの*Typeargument*の値を変更します。|
|<xref:System.Activities.Activity%601.Result%2A>|False|指定した項目がコレクションから削除されたかどうかを示す値。 結果にバインドする変数を指定するには、プロパティ グリッドで変数を入力します。|

## <a name="see-also"></a>参照
 [コレクション](../workflow-designer/collection-activity-designers.md) [addtocollection \<T >](../workflow-designer/addtocollection-t-activity-designer.md) [clearcollection \<T >](../workflow-designer/clearcollection-t-activity-designer.md)存在しない[コレクション \<T >](../workflow-designer/existsincollection-t-activity-designer.md)