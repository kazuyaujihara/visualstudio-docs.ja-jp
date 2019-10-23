---
title: プロジェクト構成オブジェクト |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project configurations, object
- objects, project configuration
ms.assetid: 877756c9-4261-43d9-9f32-51bf06b4219f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e3321b70b51d194c67f1deee8ed33e240762b16b
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72725835"
---
# <a name="project-configuration-object"></a>プロジェクト構成オブジェクト
プロジェクト構成オブジェクトは、UI への構成情報の表示を管理します。

 ![Visual Studio プロジェクトの構成](../../extensibility/internals/media/vsprojectcfg.gif "vsProjectCfg")プロジェクト構成のプロパティページ

 プロジェクト構成プロバイダーは、プロジェクト構成を管理します。 環境およびその他のパッケージは、プロジェクトの構成に関する情報にアクセスして取得するために、プロジェクト構成プロバイダーオブジェクトにアタッチされているインターフェイスを呼び出します。

> [!NOTE]
> プログラムによってソリューション構成ファイルを作成または編集することはできません。 @No__t_0 を使用する必要があります。 詳細については、「[ソリューションの構成](../../extensibility/internals/solution-configuration.md)」を参照してください。

 構成 UI で使用する表示名を公開するには、プロジェクトで <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg.get_DisplayName%2A> を実装する必要があります。 環境は <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgs%2A> を呼び出します。これにより、環境の UI に表示される構成およびプラットフォームの情報の表示名を取得するために使用できる `IVsCfg` ポインターの一覧が返されます。 アクティブな構成とプラットフォームは、アクティブなソリューション構成に格納されているプロジェクトの構成によって決まります。 @No__t_0 メソッドを使用して、アクティブなプロジェクト構成を取得できます。

 @No__t_0 オブジェクトは、必要に応じて、<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProviderEventsHelper> オブジェクトを使用して <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2> オブジェクトに実装できます。これにより、正規のプロジェクト構成名に基づいて `IVsProjectCfg2` オブジェクトを取得できます。

 プロジェクト構成へのアクセス権を持つ環境やその他のプロジェクトを提供するもう1つの方法は、プロジェクトが `IVsCfgProvider2::GetCfgs` メソッドを実装して1つ以上の構成オブジェクトを返すようにすることです。 プロジェクトは、`IVsProjectCfg` から継承し、`IVsCfg` から継承する <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2> を実装して、構成固有の情報を提供することもできます。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2> は、プロジェクト構成を追加、削除、および名前変更するためのプラットフォームと機能をサポートしています。

> [!NOTE]
> Visual Studio は2つの構成の種類に制限されなくなったため、構成を処理するコードは、構成の数についての前提を考慮して記述することはできません。また、プロジェクトが1つしかないことを前提として記述する必要もありません。構成は、必ず Debug または Retail です。 これにより、<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg.get_IsReleaseOnly%2A> と <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg.get_IsDebugOnly%2A> が使用されなくなります。

 @No__t_1 から返されたオブジェクトに対して `QueryInterface` を呼び出すと、`IVsCfgProvider2` が取得されます。 @No__t_2 project オブジェクトで `QueryInterface` を呼び出すことによって `IVsGetCfgProvider` が見つからない場合は、`IVsHierarchy::GetProperty(VSITEM_ROOT, VSHPROPID_BrowseObject)` に対して返されたオブジェクト、または構成へのポインターを使用して、階層ルートブラウザーオブジェクトの `QueryInterface` を呼び出すことによって、構成プロバイダーオブジェクトにアクセスできます。プロバイダーが `IVsHierarchy::GetProperty(VSITEM_ROOT, VSHPROPID_ConfigurationProvider)` に対して返されました。

 `IVsProjectCfg2` は、主にビルド、デバッグ、および配置管理オブジェクトへのアクセスを提供し、プロジェクトが自由に出力をグループ化できるようにします。 @No__t_0 と `IVsProjectCfg2` のメソッドを使用して、ビルドプロセスを管理するための <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg> を実装したり、構成の出力グループのポインターを <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputGroup> することができます。

 グループ内に含まれている出力の数が構成ごとに異なる場合でも、プロジェクトはサポートする構成ごとに同じ数のグループを返す必要があります。 また、グループは、プロジェクト内の構成から構成まで、同じ識別子情報 (正規名、表示名、およびグループ情報) を持っている必要があります。 詳細については、「[出力のプロジェクト構成](../../extensibility/internals/project-configuration-for-output.md)」を参照してください。

 デバッグを有効にするには、構成に <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg> を実装する必要があります。 `IVsDebuggableProjectCfg` は、プロジェクトによって実装される省略可能なインターフェイスであり、デバッガーが構成を起動し、`IVsCfg` と `IVsProjectCfg` を使用して構成オブジェクトに実装されるようにします。 ユーザーが F5 キーを押してデバッガーを起動することにした場合、環境はこれを呼び出します。

 `ISpecifyPropertyPages` と `IDispatch` は、構成に依存する情報を取得してユーザーに表示するために、プロパティページと組み合わせて使用されます。 詳細については、「[プロパティページ](../../extensibility/internals/property-pages.md)」を参照してください。

## <a name="see-also"></a>関連項目
- [構成オプションの管理](../../extensibility/internals/managing-configuration-options.md)
- [ビルドのためのプロジェクト構成](../../extensibility/internals/project-configuration-for-building.md)
- [出力のためのプロジェクト構成](../../extensibility/internals/project-configuration-for-output.md)
- [プロパティ ページ](../../extensibility/internals/property-pages.md)
- [ソリューション構成](../../extensibility/internals/solution-configuration.md)