---
title: データへの WPF コントロールのバインド |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [WPF], displaying
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio]
- displaying data, WPF
- WPF [WPF], data
- WPF Designer, data binding
- data binding, WPF
ms.assetid: e05a1e0c-5082-479d-bbc9-d395b0bc6580
caps.latest.revision: 39
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 12aad1f22fdc4badc024c62fbc302eef8e3937e4
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72670073"
---
# <a name="bind-wpf-controls-to-data-in-visual-studio"></a>Visual Studio でデータに WPF コントロールをバインドする
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

データを [!INCLUDE[TLA#tla_titlewinclient](../includes/tlasharptla-titlewinclient-md.md)] コントロールにバインドすることで、アプリケーションのユーザーに対してデータを表示できます。 これらのデータバインドコントロールを作成するには、 **[データソース]** ウィンドウから [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] の [!INCLUDE[wpfdesigner_current_short](../includes/wpfdesigner-current-short-md.md)] に項目をドラッグします。 このトピックでは、データ バインド [!INCLUDE[TLA#tla_titlewinclient](../includes/tlasharptla-titlewinclient-md.md)] アプリケーションの作成に使用できる最も一般的なタスク、ツール、およびクラスについて説明します。

 @No__t_0 でデータバインドコントロールを作成する方法に関する一般的な情報については、「 [Visual Studio でのデータへのコントロールのバインド](../data-tools/bind-controls-to-data-in-visual-studio.md)」を参照してください。 [!INCLUDE[TLA#tla_titlewinclient](../includes/tlasharptla-titlewinclient-md.md)] データ バインディングの詳細については、「[データ バインディングの概要](https://msdn.microsoft.com/library/c707c95f-7811-401d-956e-2fffd019a211)」を参照してください。

## <a name="tasks-involved-in-binding-wpf-controls-to-data"></a>データへの WPF コントロールのバインドに関連するタスク
 次の表に、 **[データ ソース]** ウィンドウから [!INCLUDE[wpfdesigner_current_short](../includes/wpfdesigner-current-short-md.md)] に項目をドラッグすることで実行できるタスクを示します。

|タスク|説明|
|----------|----------------------|
|データ バインド コントロールを作成する。<br /><br /> 既存のコントロールをデータにバインドする。|[Visual Studio でのデータへの wpf コントロールのバインドデータ](../data-tools/bind-wpf-controls-to-data-in-visual-studio2.md)[セットへの wpf コントロールのバインド](../data-tools/bind-wpf-controls-to-a-dataset.md)|
|親子のリレーションシップを持つ関連データを表示するコントロールを作成する。あるコントロールの親データ レコードを選択すると、その選択レコードに関連する子データが別のコントロールに表示されるようにします。|[WPF アプリケーションで関連データを表示する](../data-tools/display-related-data-in-wpf-applications.md)|
|あるテーブルの外部キー フィールドの値に基づいて、別のテーブルの情報を表示する*ルックアップ テーブル*を作成する。|[WPF アプリケーションでルックアップ テーブルを作成する](../data-tools/create-lookup-tables-in-wpf-applications.md)|
|コントロールをデータベース内のイメージにバインドする。|[データベースの画像にコントロールをバインドする](../data-tools/bind-controls-to-pictures-from-a-database.md)|

## <a name="valid-drop-targets"></a>有効なドロップ ターゲット
 **[データ ソース]** ウィンドウ内の項目は、[!INCLUDE[wpfdesigner_current_short](../includes/wpfdesigner-current-short-md.md)] の有効なドロップ ターゲットにのみドラッグできます。 有効なドロップ ターゲットの種類は、主にコンテナーとコントロールの 2 つです。 コンテナーとは、通常はコントロールを含むユーザー インターフェイス要素です。 たとえば、グリッドやウィンドウはコンテナーです。

## <a name="generated-xaml-and-code"></a>生成される XAML およびコード
 **[データソース]** ウィンドウから [!INCLUDE[wpfdesigner_current_short](../includes/wpfdesigner-current-short-md.md)] に項目をドラッグすると、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] によって、新しいデータバインドコントロールを定義する (または、既存のコントロールをデータソースにバインドする) [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] が生成されます。 一部のデータ ソースでは、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] により、データ ソースにデータを読み込むためのコードも分離コード ファイルに生成されます。

 次の表に、 **[データソース]** ウィンドウでデータソースの種類ごとに [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 生成される [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] とコードを示します。

|データ ソース|コントロールをデータ ソースにバインドする XAML の生成|データ ソースにデータを読み込むコードの生成|
|-----------------|-----------------------------------------------------------|--------------------------------------------------------|
|データセット|[はい]|[はい]|
|[!INCLUDE[adonet_edm](../includes/adonet-edm-md.md)]|[はい]|[はい]|
|[サービス]|[はい]|Ｘ|
|Object|[はい]|Ｘ|

### <a name="datasets"></a>データセット
 **[データソース]** ウィンドウからデザイナーにテーブルまたは列をドラッグすると、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] によって、次の操作を実行する [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] が生成されます。

- 項目をドラッグした先のコンテナーのリソースに、データセットと新しい <xref:System.Windows.Data.CollectionViewSource> を追加する。 <xref:System.Windows.Data.CollectionViewSource> は、データセットのデータの移動と表示に使用できるオブジェクトです。

- コントロールのデータ バインディングを作成する。 デザイナーの既存のコントロールに項目をドラッグすると、XAML により、その項目にコントロールがバインドされます。 項目をコンテナーにドラッグすると、XAML はドラッグした項目に対して選択されたコントロールを作成し、コントロールを項目にバインドします。 コントロールは、新しい <xref:System.Windows.Controls.Grid> 内に作成されます。

  [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] は、分離コード ファイルに次の変更も加えます。

- コントロールを格納する <xref:System.Windows.FrameworkElement.Loaded> 要素の [!INCLUDE[TLA2#tla_ui](../includes/tla2sharptla-ui-md.md)] イベント ハンドラーを作成する。 イベント ハンドラーは、テーブルにデータを読み込み、コンテナーのリソースから <xref:System.Windows.Data.CollectionViewSource> を取得して、最初のデータ項目を現在の項目にします。 @No__t_0 イベントハンドラーが既に存在する場合、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] このコードを既存のイベントハンドラーに追加します。

### <a name="entity-data-models"></a>エンティティ データ モデル
 **[データソース]** ウィンドウからデザイナーにエンティティまたはエンティティプロパティをドラッグすると、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] によって、次の操作を実行する [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] が生成されます。

- 項目をドラッグした先のコンテナーのリソースに、新しい <xref:System.Windows.Data.CollectionViewSource> を追加する。 <xref:System.Windows.Data.CollectionViewSource> は、エンティティのデータの移動と表示に使用できるオブジェクトです。

- コントロールのデータ バインディングを作成する。 デザイナーの既存のコントロールに項目をドラッグすると、[!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] により、その項目にコントロールがバインドされます。 項目をコンテナーにドラッグすると、[!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] によって、ドラッグした項目用に選択されたコントロールが作成され、そのコントロールが項目にバインドされます。 コントロールは、新しい <xref:System.Windows.Controls.Grid> 内に作成されます。

  Visual Studio は、分離コード ファイルに次の変更も加えます。

- デザイナーにドラッグされたエンティティ (または、デザイナーにドラッグされたプロパティを含むエンティティ) のクエリを返す新しいメソッドを追加する。 新しいメソッドには、Get*EntityName*Query という名前が付いています。ここで、 *EntityName*はエンティティの名前です。

- コントロールを格納する <xref:System.Windows.FrameworkElement.Loaded> 要素の [!INCLUDE[TLA2#tla_ui](../includes/tla2sharptla-ui-md.md)] イベント ハンドラーを作成する。 イベントハンドラーは、Get*EntityName*クエリメソッドを呼び出して、エンティティにデータを格納し、コンテナーのリソースから <xref:System.Windows.Data.CollectionViewSource> を取得してから、最初のデータ項目を現在の項目にします。 @No__t_0 イベントハンドラーが既に存在する場合、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] このコードを既存のイベントハンドラーに追加します。

### <a name="services"></a>Services
 サービスオブジェクトまたはプロパティを **[データソース]** ウィンドウからデザイナーにドラッグすると、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] によって、データバインドコントロールを作成する (または、既存のコントロールをオブジェクトまたはプロパティにバインドする) [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] が生成されます。 ただし、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] はプロキシ サービス オブジェクトにデータを読み込むコードを生成しません。 このコードは、ユーザーが手動で記述する必要があります。 これを行う方法を示す例については、「 [WCF データサービスへの WPF コントロールのバインド](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md)」を参照してください。

 Visual Studio は、次の処理を行う XAML を生成します。

- 項目をドラッグした先のコンテナーのリソースに、新しい <xref:System.Windows.Data.CollectionViewSource> を追加する。 <xref:System.Windows.Data.CollectionViewSource> は、サービスから返されるオブジェクトのデータの移動と表示に使用できるオブジェクトです。

- コントロールのデータ バインディングを作成する。 デザイナーの既存のコントロールに項目をドラッグすると、[!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] により、その項目にコントロールがバインドされます。 項目をコンテナーにドラッグすると、[!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] によって、ドラッグした項目用に選択されたコントロールが作成され、そのコントロールが項目にバインドされます。 コントロールは、新しい <xref:System.Windows.Controls.Grid> 内に作成されます。

### <a name="objects"></a>オブジェクト
 **[データソース]** ウィンドウからデザイナーにオブジェクトまたはプロパティをドラッグすると、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] によって、データバインドコントロールを作成する (または、既存のコントロールをオブジェクトまたはプロパティにバインドする) [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] が生成されます。 ただし、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] はオブジェクトにデータを読み込むコードを生成しません。 このコードは、ユーザーが手動で記述する必要があります。

> [!NOTE]
> カスタムクラスはパブリックである必要があり、既定ではパラメーターのないコンストラクターがあります。 構文に "ドット" を含む入れ子になったクラスにすることはできません。 詳細については、「 [WPF の XAML およびカスタムクラス](https://msdn.microsoft.com/library/e7313137-581e-4a64-8453-d44e15a6164a)」を参照してください。

 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] では、次のことを実行する [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] が生成されます。

- 項目をドラッグした先のコンテナーのリソースに、新しい <xref:System.Windows.Data.CollectionViewSource> を追加する。 <xref:System.Windows.Data.CollectionViewSource> は、オブジェクトのデータの移動と表示に使用できるオブジェクトです。

- コントロールのデータ バインディングを作成する。 デザイナーの既存のコントロールに項目をドラッグすると、XAML により、その項目にコントロールがバインドされます。 項目をコンテナーにドラッグすると、XAML はドラッグした項目に対して選択されたコントロールを作成し、コントロールを項目にバインドします。 コントロールは、新しい <xref:System.Windows.Controls.Grid> 内に作成されます。

## <a name="see-also"></a>参照
 [Visual Studio でのデータへのコントロールのバインド](../data-tools/bind-controls-to-data-in-visual-studio.md)
