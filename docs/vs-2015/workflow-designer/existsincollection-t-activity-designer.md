---
title: 存在しないコレクション &lt;T &gt; アクティビティデザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ExistsInCollection`1.UI
ms.assetid: 0acf9a13-caf5-4bb4-ba22-ec37d2b7267a
caps.latest.revision: 6
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 08aabbcb7dbef2df9a3affa8589a9c6d4205ac58
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72656733"
---
# <a name="existsincollectionlttgt-activity-designer"></a>@No__t_1 アクティビティデザイナー &lt;T 存在するコレクション
@No__t_2 アクティビティを作成および構成するには、 **\<T >** アクティビティデザイナーを使用します。

## <a name="the-existsincollectiont-activity"></a>> アクティビティ \<T 存在するコレクション
 <xref:System.Activities.Statements.ExistsInCollection%601> アクティビティでは、指定した項目が特定のコレクションに存在するかどうかを確認します。

### <a name="using-the-existsincollectiont-activity-designer"></a>> アクティビティデザイナー \<T の存在を持つコレクションの使用
 @No__t_5 の **[ツールボックス]** タブをクリックするとアクセスされる **[ツールボックス]** **の [** **コレクション**] カテゴリには、 **\<T >** アクティビティデザイナーがあります (または、 **[表示]** メニューまたは CTRL + ALT + X)

 > アクティビティデザイナー **\<T**の存在を、 **[ツールボックス]** からドラッグして、アクティビティを通常配置している任意の場所 (<xref:System.Activities.Statements.Sequence> 内など) [!INCLUDE[wfd2](../includes/wfd2-md.md)] にドロップできます。 これにより、<xref:System.Activities.Statements.ExistsInCollection%601> アクティビティが作成されます。このアクティビティには、既定の <xref:System.Activities.Activity.DisplayName%2A> の存在は \<Int32 > があります。 (既定では、 *Typeargument*は**Int32**です。 プロパティグリッドで変更できます)。 @No__t_0 の値は、存在している > アクティビティデザイナー **\<T**のヘッダー、またはプロパティグリッドの **[DisplayName]** ボックスで編集できます。 他のプロパティは、プロパティ グリッドで編集する必要があります。

### <a name="the-existsincollectiont-properties"></a>> プロパティ \<T 存在するコレクション
 次の表に、<xref:System.Activities.Statements.ExistsInCollection%601> のプロパティと、デザイナーでのその使用方法を示します。

|プロパティ名|必要|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.ExistsInCollection%601> アクティビティの表示名。 既定値は、\<Int32 > です。 <xref:System.Activities.Activity.DisplayName%2A> 値は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.ExistsInCollection%601.Item%2A>|True|コレクションに追加する項目 \<T >。 この項目*の型は型で*、型は*typeargument*です。 項目を指定するには、プロパティ グリッドで Visual Basic の式を入力します。|
|<xref:System.Activities.Statements.ExistsInCollection%601.Collection%2A>|True|項目の追加先のコレクション。 このコレクションの型は**ICollection \<TypeArgument > です。** コレクションを指定するには、プロパティ グリッドで Visual Basic の式を入力します。|
|*TypeArgument*|True|<xref:System.Collections.Generic.ICollection%601> に格納される項目の T 型。 既定では、この*Typeargument*型は**Int32**に設定されています。 型を変更するには、プロパティグリッドで、コンボボックスの*Typeargument*の値を変更します。|
|<xref:System.Activities.Activity%601.Result%2A>|False|指定した項目がコレクション内に存在するかどうかを示す値。 結果にバインドする変数を指定するには、プロパティ グリッドで Visual Basic 変数を入力します。|

## <a name="see-also"></a>参照
 [コレクション](../workflow-designer/collection-activity-designers.md) [addtocollection \<T >](../workflow-designer/addtocollection-t-activity-designer.md) [clearcollection \<T >](../workflow-designer/clearcollection-t-activity-designer.md) [removefromcollection \<T >](../workflow-designer/removefromcollection-t-activity-designer.md)