---
title: Switch &lt;T &gt; アクティビティデザイナー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.ModelItemKeyValuePair.UI
- System.Activities.Statements.Switch`1.UI
ms.assetid: 18a6c96e-49a9-4356-ab61-fbd7e3ab44bb
caps.latest.revision: 3
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: cb6d4eb189b75d6e401bca0cfe50a71081760478
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72660101"
---
# <a name="switchlttgt-activity-designer"></a>@No__t_0T &gt; アクティビティデザイナーの切り替え
<xref:System.Activities.Statements.Switch%601> アクティビティは、指定した式を評価します。そして、その評価から得られた値と一致する、関連付けられたキーを持つアクティビティを、アクティビティのコレクションから実行します。

 **スイッチ \<T >** アクティビティデザイナーを使用して、[!INCLUDE[wfd1](../includes/wfd1-md.md)] で <xref:System.Activities.Statements.Switch%601> アクティビティを作成および構成します。

## <a name="the-switchtactivity"></a>スイッチ \<T > アクティビティ
 <xref:System.Activities.Statements.Switch%601> アクティビティには、<xref:System.Activities.Statements.Switch%601.Expression%2A> と、<xref:System.Activities.Statements.Switch%601.Cases%2A> のディクショナリが含まれます。 ディクショナリ内の各ケースは、*キー*と、対応する*値*として機能するアクティビティを含むペアで構成されます。 <xref:System.Activities.Statements.Switch%601> アクティビティは、<xref:System.Activities.Statements.Switch%601.Expression%2A> を評価し、それを各キーと比較します。 一致が見つかった場合は、対応するアクティビティが実行されます。 見つかる一致は 1 つのみです。これは、ディクショナリ キーは、ディクショナリの等値比較子により定義される等価性の型に従って一意である必要があるためです。 一致が検出されない場合は、<xref:System.Activities.Statements.Switch%601.Default%2A> アクティビティが実行されます。

## <a name="how-to-use-the-switcht-activity-designer"></a>スイッチ \<T > アクティビティデザイナーの使用方法
 **切り替え \<T >** アクティビティデザイナーは、 **[ツールボックス]** の **[制御フロー]** カテゴリにあります。このカテゴリにアクセスするには、[!INCLUDE[wfd2](../includes/wfd2-md.md)] の **[ツールボックス]** タブをクリックします (または、ビューから **[ツールバー]** を選択します。メニューまたは CTRL + ALT + X)@No__t_8 にドロップすると、 **[型の選択**] ダイアログボックスが表示され、ユーザーは 1 アクティビティで使用されるジェネリック型*t*を指定できます。 既定値は**Int32**です。 ジェネリック型*T*が選択されると、 **> デザイナー \<T スイッチ**がワークフローデザイナーに追加されます。

 **Switch \<T >** デザイナーのプロパティを次に示します。 これらのプロパティはすべて、プロパティ グリッドで編集できます。 一部のプロパティは、デザイナー画面で設定することもできます。

 次の表に、最も役に立つ <xref:System.Activities.Statements.Switch%601> プロパティと、デザイナーでのその使用方法を示します。

|プロパティ名|必要|使用方法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Switch%601> アクティビティ デザイナーの表示名を指定します。 既定値は、Switch \<Int32 > です。 この値は、 **[プロパティ]** ウィンドウで編集することも、デザイナーヘッダーで直接編集することもできます。<br /><br /> <xref:System.Activities.Activity.DisplayName%2A> は必須ではありませんが、使用することをお勧めします。|
|<xref:System.Activities.Statements.Switch%601.Expression%2A>|True|cases コレクション内のキーを比較して、実行する case を決定するために使用される式を指定します。|
|<xref:System.Activities.Statements.Switch%601.Default%2A>||一致が検出されなかった場合に実行するアクティビティを指定します。 デザイナーの **[アクティビティの追加]** ボタンをクリックして、アクティビティをドロップできる**既定**のボックスを開きます。|
|<xref:System.Activities.Statements.Switch%601.Cases%2A>||評価する case を指定します。 ケースを追加するには、スイッチ の下部にある **新しいケースの追加** ボタンをクリックし **\<T >** デザイナー をクリックします。 ボタンがテキストボックスに変わります (スイッチ \<T > を追加するときに選択したジェネリック型が String または Enum の場合)。 **[ケースの値]** ボックスにキーを追加すると、ケース領域が展開され、"ここにアクティビティをドロップします" というヒントテキストが表示されたら、ケースの実行ロジックを定義します。|

 case キーが重複しない限り、複数の case を追加できます。 case キーが重複している場合は、エラー ダイアログが表示され、指定した case キーが既に存在しているために別のキーを選択する必要があることが示されます。 > デザイナー **\<T スイッチ**では、一度に1つのケース領域のみを展開ビューに配置できます。 折りたたまれたビューに case の領域が表示されている場合は、case の領域をクリックすると展開されます。 case が折りたたまれており、この case 内にアクティビティが存在する場合は、このアクティビティの表示名が右側に表示されます。 それ以外の場合は、 **[アクティビティの追加]** ボタンが表示され、クリックするとケースが展開され、アクティビティを追加できるようになります。

 既存の case のキーをクリックすると、キーがラベルからテキスト ボックスに変わり、case キーを編集できます。

 case を削除する方法には、次の 2 つがあります。

1. case を選択して削除します。

2. ケースを選択し、右クリックしてコンテキストメニューを表示し、 **[削除]** を選択します。

   case を削除するには、case 自体を選択する必要があることに注意してください。 case 内のアクティビティを選択して削除すると、case ではなく、アクティビティのみが削除されます。

## <a name="see-also"></a>参照
 [制御フロー](../workflow-designer/control-flow-activity-designers.md)