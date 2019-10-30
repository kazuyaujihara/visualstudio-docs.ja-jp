---
title: プロパティページ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- configuration options, changing properties
- property pages
- property pages, changing configuration options
ms.assetid: b9b3e6e8-1e30-4c89-9862-330265dcf38c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 51487b35686da9676f201a157ddb8e47afb75ce8
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72725055"
---
# <a name="property-pages"></a>[プロパティ ページ]
ユーザーは、プロパティページを使用して、プロジェクトの構成に依存し、依存しないプロパティを表示および変更できます。 選択したオブジェクトのプロパティページビューを提供するオブジェクトの**プロパティウィンドウまた**はソリューションエクスプローラーツールバーで、 **[プロパティページ]** ボタンが有効になります。 プロパティページは環境によって作成され、ソリューションとプロジェクトで使用できます。 ただし、構成に依存するプロパティを使用するプロジェクトアイテムに対しても使用できます。 この機能は、プロジェクト内のファイルが、正しくビルドするために異なるコンパイラスイッチ設定を必要とする場合に使用できます。

## <a name="using-property-pages"></a>プロパティページの使用
 プロパティページが既に表示されていて、選択内容が変更された場合 (たとえば、ソリューションからプロジェクトに変更した場合)、ページに表示される情報が変更され、新しい選択項目のプロパティが表示されます。 プロパティページをサポートするプロパティがオブジェクトに存在しない場合、プロパティページは空になります。

 複数のオブジェクトが選択されている場合、プロパティページには、選択したすべての項目のプロパティの共通部分が表示されます。 選択した項目に構成に依存するプロパティが含まれておらず、ソリューションエクスプローラー ツールバーの **プロパティページ** ボタンがクリックされると、プロパティウィンドウにフォーカスが移動します。 プロパティウィンドウと選択に関する詳細については、「[プロパティの拡張](../../extensibility/internals/extending-properties.md)」を参照してください。

 複数のオブジェクトに対してプロパティが表示され、プロパティページで値を変更した場合、オブジェクトのすべての値は、最初は異なる場合でも新しい値に設定され、個々のオブジェクトのプロパティが表示されたときにそのページは空白になります。

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]で使用できる **[Projectproperty Pages]** ダイアログボックスには、次の2つの一般的な種類があります。 たとえば、Visual Basic プロジェクトでは、次のスクリーンショットに示すように、フィールド形式を使用してプロパティページが表示されます。 2番目のセクションでは、プロパティページが、[プロパティ] ウィンドウに表示されるのと同様のプロパティグリッドをホストしています。

 ![Visual Basic プロパティページ](../../extensibility/internals/media/vsvbproppages.gif "vsVBPropPages")フィールド形式とツリー構造を持つ [プロジェクトプロパティページ] ダイアログボックス

 [プロパティページ] ダイアログボックスのツリー構造は、<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>を使用して作成されません。 環境は、<xref:Microsoft.VisualStudio.OLE.Interop.ISpecifyPropertyPages> によって渡されるレベル名と <xref:Microsoft.VisualStudio.Shell.Interop.IVsPropertyPage> インターフェイスに基づいて構築されます。

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] のプロパティページで使用できるトップレベルのカテゴリは2つだけです。

- [共通プロパティ]: 選択したオブジェクトの構成に依存しない情報が表示されます。 その結果、[共通プロパティ] サブカテゴリの1つを選択した場合、ダイアログボックスの上部にある [構成]、[プラットフォーム]、および [Configuration Manager] オプションは使用できません。

- 構成プロパティ。ソリューションまたはプロジェクトのデバッグ、最適化、およびビルドパラメーターに関連する構成に依存する情報が含まれています。

  追加の最上位レベルのカテゴリを作成することはできませんが、`IVsPropertyPage`の実装に表示しないように選択できます。 たとえば、オブジェクトに対して表示する構成に依存しないプロパティがない場合は、[共通プロパティ] カテゴリを表示しないように選択できます。 構成オブジェクト (`IVsCfg`、`IVsProjectCfg`、および関連するインターフェイスを実装するオブジェクト) に `ISpecifyPropertyPages` を実装するときに、項目の参照オブジェクトと構成プロパティから `ISpecifyPropertyPages` が実装されている場合は、共通プロパティを表示します。

  最上位レベルのカテゴリの下に表示される各カテゴリは、個別のプロパティページを表します。 ダイアログボックスで使用できるカテゴリおよびサブカテゴリのエントリは、`ISpecifyPropertyPages` と `IVsPropertyPage`の実装によって決まります。

  プロパティページに表示されるプロパティを持つ選択コンテナー内の項目の `IDispatch` オブジェクトは、クラス Id の一覧を列挙する `ISpecifyPropertyPages` を実装します。 クラス Id は `ISpecifyPropertyPages` に変数として渡され、プロパティページをインスタンス化するために使用されます。 クラス Id の一覧も `IVsPropertyPage` に渡され、ダイアログボックスの左側にツリー構造が作成されます。 次に、プロパティページは `ISpecifyPropertyPages` を実装する `IDispatch` オブジェクトに情報を渡し、各ページの情報を入力します。

  参照オブジェクトのプロパティは、選択コンテナー内の各オブジェクトの `IDispatch` を使用して取得されます。

  VSPackage に `Help::DisplayTopicFromF1Keyword` を実装すると、[ヘルプ] ボタンの機能が提供されます。

  詳細については、MSDN ライブラリの「`IDispatch`」および「`ISpecifyPropertyPages`」を参照してください。

  サンプルに表示されるプロパティページの2番目の種類は、次のスクリーンショットに示すように、プロパティグリッドのフォームをホストします。

  ![VC プロパティページ](../../extensibility/internals/media/vsvcproppages.gif "vsVCPropPages")プロパティグリッドがある [プロパティページ] ダイアログボックス

  インターフェイス `IVSMDPropertyBrowser` および `IVSMDPropertyGrid` (vsmanaged .h で宣言) は、ダイアログボックスまたはウィンドウ内でプロパティグリッドを作成および設定するために使用されます。

  プロジェクトのアーキテクチャは、以前のバージョンの [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]から大幅に変更されています。 特に、アクティブなプロジェクトの概念は変更されています。 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]には、アクティブなプロジェクトの概念はありません。 以前の開発環境では、コンテキストに関係なく、ビルドおよび配置コマンドが既定で適用されるプロジェクトとして、アクティブなプロジェクトがありました。 ここで、ソリューションによって、ビルドおよび配置コマンドがどのプロジェクトに適用されるかを制御および判別します。

  以前にアクティブなプロジェクトは、次の3つの方法のいずれかでキャプチャされるようになりました。

- スタートアッププロジェクト

   ユーザーが F5 キーを押したとき、または [ビルド] メニューの [実行] を選択したときに開始される、ソリューションのプロパティページからプロジェクトまたはプロジェクトを指定できます。 これは、古いアクティブプロジェクトと同様の方法で動作します。これは、名前が太字のフォントでソリューションエクスプローラーに表示されることを意味します。

   スタートアッププロジェクトは、`DTE.Solution.SolutionBuild.StartupProjects`を呼び出すことによって、オートメーションモデルのプロパティとして取得できます。 VSPackage では、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2.get_StartupProject%2A> または <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2.get_StartupProject%2A> メソッドを呼び出します。 `IVsSolutionBuildManager` は、SID_SVsSolutionBuildManager で `QueryService` ことによってサービスとして利用できます。 詳細については、「[プロジェクト構成オブジェクト](../../extensibility/internals/project-configuration-object.md)と[ソリューション構成](../../extensibility/internals/solution-configuration.md)」を参照してください。

- アクティブソリューションビルド構成

   [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] には、アクティブなソリューション構成があります。この構成は、`DTE.Solution.SolutionBuild.ActiveConfiguration`を実装することによって、オートメーションモデルで使用できます。 ソリューション構成は、ソリューション内のプロジェクトごとに1つのプロジェクト構成を含むコレクションです (各プロジェクトは複数の構成を持つことができ、複数のプラットフォームでは名前が異なる場合があります)。 ソリューションのプロパティページに関する詳細については、「[ソリューションの構成](../../extensibility/internals/solution-configuration.md)」を参照してください。

- 現在選択されているプロジェクト

   プロジェクト階層とプロジェクト項目、または選択した項目を取得するには、<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCurrentSelection%2A> メソッドを実装します。 DTE からは、`SelectedItems.SelectedItem.Project` メソッドと `SelectedItems.SelectedItem.ProjectItem` メソッドを使用します。 コア [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ドキュメントには、これらの見出しの下にサンプルコードがあります。

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPropertyPage>
- [構成オプションの管理](../../extensibility/internals/managing-configuration-options.md)
- [プロジェクト構成オブジェクト](../../extensibility/internals/project-configuration-object.md)
- [ソリューション構成](../../extensibility/internals/solution-configuration.md)