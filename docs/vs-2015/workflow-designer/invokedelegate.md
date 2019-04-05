---
title: InvokeDelegate |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- InvokeDelegate Designer
- System.Activities.Statements.InvokeDelegate.UI
ms.assetid: 289a7498-5127-453f-beb5-05f05b80d26f
caps.latest.revision: 3
author: steved0x
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 30281d8cd5d5ed94ed89a980006f9618292a778d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977818"
---
# <a name="invokedelegate"></a>InvokeDelegate

**InvokeDelegate**を作成および構成デザイナーを使用する<xref:System.Activities.Statements.InvokeDelegate>アクティビティ。

## <a name="the-invokedelegate-activity"></a>InvokeDelegate アクティビティ

<xref:System.Activities.Statements.InvokeDelegate> はパブリック デリゲートを呼び出します。

### <a name="using-the-invokedelegate-activity-designer"></a>InvokeDelegate アクティビティ デザイナーの使用

**InvokeDelegate**アクティビティ デザイナーが記載されて、**プリミティブ**のカテゴリ、**ツールボックス**をクリックしてアクセスする、**ツールボックス**タブ[!INCLUDE[wfd2](../includes/wfd2-md.md)](または、選択**ツールバー**から、**ビュー**メニューのまたは CRTL + ALT + X)。

**InvokeDelegate**からアクティビティ デザイナーをドラッグすることができます、**ツールボックス**ドロップ、[!INCLUDE[wfd2](../includes/wfd2-md.md)]サーフェス場所、アクティビティを通常配置など内、<xref:System.Activities.Statements.Sequence>します。 この操作により、InvokeDelegate という既定の <xref:System.Activities.Statements.InvokeDelegate> を持つ <xref:System.Activities.Activity.DisplayName%2A> アクティビティが作成されます。 <xref:System.Activities.Activity.DisplayName%2A>のヘッダーで編集できる、 **InvokeDelegate**アクティビティ デザイナーまたは、 **DisplayName**プロパティ グリッドのボックスです。

### <a name="the-invokedelegate-properties"></a>InvokeDelegate プロパティ

次の表に、<xref:System.Activities.Statements.InvokeDelegate> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティ グリッドで編集できます。また、その一部は[!INCLUDE[wfd2](../includes/wfd2-md.md)]のデザイナー画面で編集できます。

|プロパティ名|必須|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.InvokeDelegate> アクティビティの表示名。 既定値は InvokeDelegate です。<br /><br /> <xref:System.Activities.Activity.DisplayName%2A> は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|True|アクティビティの実行時に呼び出す <xref:System.Activities.ActivityDelegate> の名前。 このプロパティは、デザイナー画面で設定することもできます。 これは必須プロパティです。|
|<<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|呼び出されたデリゲートの引数コレクション。 キーは <xref:System.Activities.DelegateArgument> の <xref:System.Activities.ActivityDelegate> オブジェクトの名前であり、値は、式が評価され対応する <xref:System.Activities.DelegateArgument> オブジェクトに割り当てられる引数です。 プロパティ グリッドで、省略記号ボタンをクリックします。、 **DelegateArguments**フィールドが表示されます、 **DelegateArguments**ダイアログ ボックスを使用するこのプロパティを設定できます。 をクリックして、**引数の作成**引数を追加するフィールド。|

## <a name="see-also"></a>関連項目

- [方法: ワークフロー デザイナーでアクティビティ デリゲートを定義および使用する](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)