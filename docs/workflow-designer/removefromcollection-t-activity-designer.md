---
title: ワークフローデザイナー-RemoveFromCollection &lt;T &gt; アクティビティデザイナー
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.RemoveFromCollection`1.UI
ms.assetid: 6617ba26-c8bc-4aed-b746-112bf490d288
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1a8885505607d654327ad9dc36ab88708ab708c3
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72649998"
---
# <a name="removefromcollectiont-activity-designer"></a>RemoveFromCollection \<T > アクティビティデザイナー

@No__t_2 アクティビティを作成および構成するには、 **Removefromcollection \<T >** アクティビティデザイナーを使用します。

## <a name="the-removefromcollectiontactivity"></a>RemoveFromCollection \<T > アクティビティ

<xref:System.Activities.Statements.RemoveFromCollection%601> アクティビティは、指定した項目を特定のコレクションから削除します。

### <a name="using-the-removefromcollectiont-activity-designer"></a>RemoveFromCollection \<T > アクティビティデザイナーの使用

**[ツールボックス]** の **[コレクション]** カテゴリにある > アクティビティデザイナー **\<T removefromcollection**にアクセスします。
**Removefromcollection \<T >** アクティビティデザイナーは、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) ワークフローデザイナーにドロップできます。 これにより、既定の <xref:System.Activities.Activity.DisplayName%2A> RemoveFromCollection < Int32 \> を持つ <xref:System.Activities.Statements.RemoveFromCollection%601> アクティビティが作成されます。 @No__t_0 値は、 **Removefromcollection < t \>** アクティビティデザイナーのヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。 他のプロパティは、プロパティ グリッドで編集する必要があります。

### <a name="the-removefromcollectiont-properties"></a>RemoveFromCollection < T \> プロパティ

次の表は、<xref:System.Activities.Statements.RemoveFromCollection%601> のプロパティと、デザイナーでのそれらの使用方法を示しています。

|プロパティ名|必要|使用方法|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.RemoveFromCollection%601> アクティビティの省略可能な表示名。 既定値は、RemoveFromCollection < Int32 \> です。<br /><br /> <xref:System.Activities.Activity.DisplayName%2A> は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Item%2A>|True|コレクションから削除する項目 **\<T >** 。 この項目の型は*T*で、 *typeargument*型です。 項目を指定するには、プロパティ グリッドで Visual Basic の式を入力します。|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Collection%2A>|True|項目を削除するコレクション。 このコレクションの型は**ICollection < TypeArgument \> です。** コレクションを指定するには、プロパティグリッドで Visual Basic 式を入力します。|
|*TypeArgument*|True|<xref:System.Collections.Generic.ICollection%601> に格納される項目の T 型。 既定では、この*Typeargument*型は**Int32**に設定されています。 型を変更するには、プロパティグリッドで、コンボボックスの*Typeargument*の値を変更します。|
|<xref:System.Activities.Activity%601.Result%2A>|False|指定した項目がコレクションから削除されたかどうかを示す値。 結果にバインドする変数を指定するには、プロパティ グリッドで変数を入力します。|

## <a name="see-also"></a>関連項目

- [コレクション](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T>](../workflow-designer/addtocollection-t-activity-designer.md)
- [ClearCollection\<T>](../workflow-designer/clearcollection-t-activity-designer.md)
- [ExistsInCollection\<T>](../workflow-designer/existsincollection-t-activity-designer.md)