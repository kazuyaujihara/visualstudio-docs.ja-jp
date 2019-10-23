---
title: ワークフロー デザイナーで検索を使用する方法
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f42d3115-2ed2-4941-8f1e-92dac41c30fa
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
author: jillre
ms.openlocfilehash: 12bda4af085b8ab41d3e11841f24cd5dfd389738
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650294"
---
# <a name="how-to-use-search-in-the-workflow-designer"></a>ワークフロー デザイナーで検索を使用する方法

より大規模で複雑なワークフローの作成を容易にするために、ワークフローデザイナー内で検索して、キーワードによって項目を検索することができます。 デザイナーでは、置換はサポートされないことに注意してください。

## <a name="quick-find"></a>クイック検索

クイック検索では、デザイナーで次のものが検索されます。

- <xref:System.Activities.Activity> オブジェクト、<xref:System.Activities.Statements.FlowNode> オブジェクト、<xref:System.Activities.Statements.State> オブジェクト、遷移、およびその他のカスタム フロー制御項目のプロパティ。

- 変数

- 引数

- 式

### <a name="use-quick-find"></a>クイック検索を使用する

1. ワークフローデザイナーを開いた状態で、Ctrl キーを押し**ながら F**キーを押すか、 **[編集]** を選択して [**クイック検索** > **検索  >  置換**] を選択します。

2. 検索する **[文字列]** ボックスに検索語句を入力し、 **[次を検索]** をクリックします。

3. 検索用語は、現在のワークフローにあります。 次の図は、デザイナーに配置されているアクティビティの表示名を示しています。

   ![ワークフロー デザイナーでの検索結果](../workflow-designer/media/designersearch.png)

## <a name="find-in-files"></a>フォルダーを指定して検索する

[フォルダーを検索] XAML ファイルを含むワークフローファイル内の文字列を検索します。

### <a name="use-find-in-files"></a>フォルダーを使用して検索

1. Visual Studio で、 **Ctrl**キーを押し +**Shift**キーを押し +**F**を押すか、[ > **編集**] を選択して [**フォルダーを** **検索し** >  検索] を選択します。

2. 検索する **[文字列]** ボックスに検索項目を入力し、 **[すべて検索]** をクリックします。

3. 検索結果は、 **[検索結果]** ビューに表示されます。 結果項目をダブルクリックすると、ワークフローデザイナーでの一致を含むアクティビティに移動します。