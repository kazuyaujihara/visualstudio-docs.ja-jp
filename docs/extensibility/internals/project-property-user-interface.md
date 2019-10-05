---
title: プロジェクトプロパティのユーザーインターフェイス |Microsoft Docs
ms.date: 03/22/2018
ms.topic: conceptual
helpviewer_keywords:
- project properties [Visual Studio], user interface
- projects [Visual Studio SDK], properties UI
- project properties UI
ms.assetid: b6aec634-8533-476c-9ebd-36536a2288e2
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a83e5c9fb633322da536e62f1ba03484b965b162
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71252364"
---
# <a name="project-property-user-interface"></a>プロジェクト プロパティのユーザー インターフェイス

プロジェクトのサブタイプは、プロジェクトの **[プロパティページ]** ダイアログボックスで、基本プロジェクトによって指定されている項目を使用したり、指定どおりに読み取り専用のコントロールやページ全体を表示または非表示にしたり、 **[プロパティページ]** ダイアログにプロジェクトのサブタイプ固有のページを追加したりできます。箱.

## <a name="extending-the-project-property-dialog-box"></a>[プロジェクトプロパティ] ダイアログボックスの拡張

プロジェクトのサブタイプは、オートメーションエクステンダーとプロジェクト構成の参照オブジェクトを実装します。 これらのエクステンダーは<xref:EnvDTE.IFilterProperties> 、特定のプロパティを非表示または読み取り専用にするためのインターフェイスを実装しています。 基本プロジェクトの **[プロパティページ]** ダイアログボックスでは、基本プロジェクトによって実装され、オートメーションエクステンダーによって実行されるフィルター処理が優先されます。

**プロジェクトプロパティ**ダイアログボックスを拡張するプロセスを次に示します。

- 基本プロジェクトは、 <xref:EnvDTE80.IInternalExtenderProvider>インターフェイスを実装することで、プロジェクトのサブタイプからエクステンダーを取得します。 基本プロジェクトの [参照]、[プロジェクトオートメーション]、[プロジェクト構成] の各オブジェクトは、このインターフェイスを実装します。

- プロジェクト参照オブジェクト<xref:EnvDTE80.IInternalExtenderProvider>のの実装と、プロジェクトのサブタイプアグリゲーターの<xref:EnvDTE80.IInternalExtenderProvider>実装に対するプロジェクトオートメーションオブジェクトのデリゲート`QueryInterface` ( <xref:EnvDTE80.IInternalExtenderProvider> <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>つまり、プロジェクトオブジェクト)。

- 基本プロジェクト構成の参照オブジェクトは、 <xref:EnvDTE80.IInternalExtenderProvider>プロジェクトのサブタイプ構成オブジェクトからオートメーションエクステンダーに直接接続するためにも実装します。 その実装は、プロジェクト<xref:EnvDTE80.IInternalExtenderProvider>のサブタイプアグリゲーターによって実装されるインターフェイスに委任されます。

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetProjectItem%2A>は、プロジェクト構成参照オブジェクトによって実装さ<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>れ、オブジェクトを返します。

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetCfg%2A>は、プロジェクト構成参照オブジェクトによっても実装さ<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg>れ、オブジェクトを返します。

- プロジェクトのサブタイプは、次<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>の値を取得することによって、実行時に基本プロジェクトのさまざまな拡張可能なオブジェクトの適切な catid を特定できます。

  - <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2.VSHPROPID_ExtObjectCATID>

  - <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2.VSHPROPID_BrowseObjectCATID>

  - <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2.VSHPROPID_CfgBrowseObjectCATID>

プロジェクトスコープの Catid を決定するために、プロジェクトのサブタイプは VSITEMID の上のプロパティを取得し[ます。](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)からのルート`VSITEMID typedef`。 プロジェクトのサブタイプでは、プロジェクトに対して表示される **[プロパティページ]** ダイアログボックスのページを制御する必要がある場合もあります。構成依存と構成に依存しません。 一部のプロジェクトのサブタイプでは、組み込みページを削除し、プロジェクトのサブタイプに固有のページを追加する必要がある場合があります。 これを有効にするために、マネージクライアントプロジェクトは<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> 、次のプロパティのメソッドを呼び出します。

- `VSHPROPID_PropertyPagesCLSIDList`—構成に依存しないプロパティページの Clsid をセミコロンで区切った一覧。

- `VSHPROPID_CfgPropertyPagesCLSIDList —`構成に依存するプロパティページの Clsid をセミコロンで区切った一覧。

プロジェクトのサブタイプによっ<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>てオブジェクトが集約されるため、これらのプロパティの定義をオーバーライドして、どの**プロパティページ**のダイアログボックスを表示するかを制御できます。 プロジェクトのサブタイプは、これらのプロパティを内部基本プロジェクトから取得し、必要に応じて Clsid を追加または削除できます。

プロジェクトのサブタイプによって追加された新しいプロパティページには、プロジェクト構成の参照オブジェクトが基本プロジェクトの実装から渡されます。 このプロジェクト構成の参照オブジェクトは、オートメーションエクステンダーをサポートしています。 AutomationExtenders の詳細については、「[オートメーションエクステンダーの実装と使用](https://msdn.microsoft.com/Library/0d5c218c-f412-4b28-ab0c-33a611f62356)」を参照してください。 プロジェクトのサブタイプの呼び出し<xref:EnvDTE.Project.Extender%2A>によって実装されるプロパティページでは、基本プロジェクトの構成参照オブジェクトを拡張する独自のプロジェクトサブタイプの構成参照オブジェクトを取得します。

## <a name="see-also"></a>関連項目

- <xref:EnvDTE.IFilterProperties>
- [[プロパティページ] ダイアログボックス](/previous-versions/visualstudio/visual-studio-2010/as5chysf(v=vs.100))
