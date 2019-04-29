---
title: 基本プロジェクトのオブジェクト モデルの拡張 |Microsoft Docs
ms.date: 03/22/2018
ms.topic: conceptual
helpviewer_keywords:
- automation object model, extending
- project subtypes, extending automation object model
- automation object model
ms.assetid: 2f95cc53-dff6-476c-bacd-500fb0ff7725
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c148a675dbf4a5602ce620042d488e19127c09ca
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62909969"
---
# <a name="extend-the-object-model-of-the-base-project"></a>ベースのプロジェクトのオブジェクト モデルを拡張します。

プロジェクト サブタイプを次の場所ベースのプロジェクトのオートメーション オブジェクト モデルを拡張可能性があります。

- Project.Extender("\<ProjectSubtypeName>"):これにより、プロジェクトのサブタイプのカスタム メソッドを使用するオブジェクトを提供する、<xref:EnvDTE.Project>オブジェクト。 プロジェクト サブタイプは、オートメーション エクステンダーを使用して公開することができます、`Project`オブジェクト。 <xref:EnvDTE80.IInternalExtenderProvider>メイン プロジェクト サブタイプ アグリゲーターで実装されるインターフェイスの場合は、そのオブジェクトを提供する必要があります、`VSHPROPID_ExtObjectCATID`から<xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2>(に対応する、 `itemid` @property [VSITEMID します。ルート](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID.Root>)) CATID。

- ProjectItem.Extender("\<ProjectSubtypeName>"):これにより、カスタム メソッドの特定のオブジェクトを提供するプロジェクト サブタイプ<xref:EnvDTE.ProjectItem>プロジェクト内のオブジェクト。 プロジェクト サブタイプは、オートメーション エクステンダーを使用して、このオブジェクトを公開します。 <xref:EnvDTE80.IInternalExtenderProvider>メイン プロジェクト サブタイプ アグリゲーターで実装されるインターフェイスをそのオブジェクトを提供する必要があります、`VSHPROPID_ExtObjectCATID`から<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>(を目的に対応する<xref:Microsoft.VisualStudio.VSConstants.VSITEMID>) CATID。

- Project.Properties:このコレクションの構成に依存しないプロパティを公開する、`Project`オブジェクト。 `Project` プロパティについて詳しくは、「<xref:EnvDTE.Project.Properties%2A>」をご覧ください。 プロジェクト サブタイプは、オートメーション エクステンダーを使用して、そのプロパティをこのコレクションに追加します。 <xref:EnvDTE80.IInternalExtenderProvider>メイン プロジェクト サブタイプ アグリゲーターで実装されるインターフェイスをそのオブジェクトを提供する必要があります、`VSHPROPID_BrowseObjectCATID`から<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>(に対応する、 `itemid` @property [VSITEMID します。ルート](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID.Root>)) CATID。

- Configuration.Properties:このコレクションは、特定の構成 (たとえば、デバッグなど) のプロジェクトの構成に依存するプロパティを公開します。 詳細については、「 <xref:EnvDTE.Configuration> 」を参照してください。 プロジェクト サブタイプは、オートメーション エクステンダーを使用して、そのプロパティをこのコレクションに追加します。 <xref:EnvDTE80.IInternalExtenderProvider> CATID をメイン プロジェクト サブタイプ アグリゲーターで実装されるインターフェイスは、そのオブジェクトを提供`VSHPROPID_CfgBrowseObjectCATID`(に対応する、 `itemid` @property [VSITEMID します。ルート](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID.Root>))。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>インターフェイスが別の 1 つの構成の参照オブジェクトを区別するために使用されます。

## <a name="see-also"></a>関連項目

- <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>