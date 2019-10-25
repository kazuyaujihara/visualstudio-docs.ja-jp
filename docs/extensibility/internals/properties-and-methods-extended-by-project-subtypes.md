---
title: プロジェクトのサブタイプによって拡張されたプロパティとメソッド |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project subtypes, extended methods
- project subtypes, extended properties
ms.assetid: 2b9833bf-8551-4ae1-93db-197ba645c65e
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2f5f67ac70b7ca6d5151a9115f20be88f6984d52
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72725338"
---
# <a name="properties-and-methods-extended-by-project-subtypes"></a>プロジェクト サブタイプによって拡張されるプロパティとメソッド
プロジェクトのサブタイプは、基本プロジェクトのアグリゲーターとして構築されるため、プロジェクトの動作に大きな影響を与えます。 このセクションでは、プロジェクトのサブタイプによって強化または変更できる機能の一部をまとめます。

## <a name="features-gained-by-aggregation"></a>集計によって得られる機能
 次の表は、集計によってプロジェクトのサブタイプが基本プロジェクトでオーバーライドできる多くのメソッドをまとめたものです。

|集計によってオーバーライドされるメソッド|プロジェクトのサブタイプ|
|---------------------------------------|---------------------|
|@No__t_0 から:<br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.SetProperty%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetGuidProperty%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.SetGuidProperty%2A>|プロジェクトのサブタイプを<br /><br /> -プロジェクトノードのキャプションとアイコンを変更します。<br />-Project `Browse` オブジェクトを完全にオーバーライドします。<br />-プロジェクトの名前を変更できるかどうかを制御します。<br />-制御の並べ替え順序。<br />-ダイナミックヘルプのユーザーコンテキストを制御します。|
|@No__t_0 から:<br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.GetItemContext%2A>|デザイナーおよびエディターに提供されるコンテキストサービスをプロジェクトのサブタイプで制御できるようにします。|
|@No__t_0 から:<br /><br /> <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A><br /><br /> <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>|プロジェクトのサブタイプを<br /><br /> -Project コマンドのコマンドルーティングに参加します。<br />-プロジェクトのアンビエントコマンドとソリューションエクスプローラーアクティブなコマンドの両方を追加、削除、または無効にします。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>|**[新しい項目の追加]** ダイアログボックスでユーザーに表示される内容をプロジェクトのサブタイプでフィルター処理できるようにします。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGeneratorFactory>|プロジェクトのサブタイプを<br /><br /> -ファイル拡張子が指定された既定のジェネレーターを特定します。<br />-人間が判読できるジェネレーター名を COM オブジェクトにマップします。|

## <a name="properties-used-by-project-subtypes"></a>プロジェクトのサブタイプで使用されるプロパティ
 環境と基本プロジェクトシステムでは、次の表に記載されている <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID> および <xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2> 列挙型のプロパティを使用して、プロジェクトのサブタイプがプロジェクトシステムのさまざまな機能を制御できるようにします。

|VSHPROPID プロパティ|プロジェクトのサブタイプ|
|------------------------|---------------------|
|`AddItemTemplatesGuid`|プロジェクトのサブタイプで **[項目の追加]** ダイアログボックスの内容を制御できるようにします。 プロジェクトのサブタイプでは、テンプレートディレクトリの新しい仕様を指定したり、新しい種類の項目を追加したり、既存の項目を削除したり、基本プロジェクトの **[項目の追加]** ダイアログボックスで項目のサブセットを再編成したりできます。|
|`PropertyPagesCLSIDList`|プロジェクトのサブタイプが、構成に依存しないプロパティページを追加または削除できるようにします。|
|`CfgPropertyPagesCLSIDList`|プロジェクトのサブタイプが、構成に依存するプロパティページを追加または削除できるようにします。|
|`ExtObjectCATID`|プロジェクトのサブタイプが、エクステンダーの CATID を知って、プロジェクトまたはプロジェクト項目オブジェクトのオートメーションエクステンダーを提供できるようにします。 たとえば、プロジェクトのサブタイプは、カスタム `Project.Extender("<subtype>")` オブジェクトを提供できます。|
|`BrowseObjectCATID`|Extender の CATID を知っていることで、プロジェクトのサブタイプが `Browse` オブジェクトのオートメーションエクステンダーを提供できるようにします。 たとえば、プロジェクトのサブタイプでは、<xref:EnvDTE.Project.Properties%2A> コレクションに追加のプロパティを追加できます。|
|`CfgBrowseObjectCATID`|プロジェクトのサブタイプが、プロジェクト構成参照オブジェクトのオートメーションエクステンダーを提供できるようにします。 たとえば、プロジェクトのサブタイプでは、<xref:EnvDTE.Configuration.Properties%2A> コレクションに追加のプロパティを追加できます。|
|`CfgExtObjectCATID`|プロジェクトのサブタイプが構成オブジェクトのオートメーションエクステンダーを提供できるようにします。|
|`DefaultPlatformName`|プロジェクトの構成オブジェクトのプラットフォーム名をプロジェクトのサブタイプで判断できるようにします。|

 基本プロジェクトは、上記のプロパティの既定の実装を提供します。 基本プロジェクトは、最も外側のプロジェクトのサブタイプの <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> に対して `QueryInterface` を呼び出すことによってこれらのプロパティを取得します。これにより、プロジェクトのサブタイプでプロパティの実装をオーバーライドできます。

## <a name="see-also"></a>関連項目
- [プロジェクト サブタイプのデザイン](../../extensibility/internals/project-subtypes-design.md)