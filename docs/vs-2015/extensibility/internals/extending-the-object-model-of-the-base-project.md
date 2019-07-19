---
title: 基本プロジェクトのオブジェクト モデルの拡張 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- automation object model, extending
- project subtypes, extending automation object model
- automation object model
ms.assetid: 2f95cc53-dff6-476c-bacd-500fb0ff7725
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7723881bce81824b66a936793175077a0ec67666
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68187163"
---
# <a name="extending-the-object-model-of-the-base-project"></a>ベース プロジェクトのオブジェクト モデルの拡張
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

プロジェクト サブタイプを次の場所ベースのプロジェクトのオートメーション オブジェクト モデルを拡張可能性があります。  
  
- Project.Extender ("\<ProjectSubtypeName >") – これにより、プロジェクトのサブタイプのカスタム メソッドを使用するオブジェクトを提供する、<xref:EnvDTE.Project>します。 プロジェクト サブタイプは、オートメーション エクステンダーを使用して公開することができます、`Project`オブジェクト。 <xref:EnvDTE80.IInternalExtenderProvider>メイン プロジェクト サブタイプ アグリゲーターで実装されるインターフェイスの場合は、そのオブジェクトを提供する必要があります、`VSHPROPID_ExtObjectCATID`から<xref:Microsoft.VisualStudio.Shell.Interop.__VSSPROPID2>(に対応する、 `itemid` VSITEMID_ROOT の値から`VSITEMID`) CATID。  
  
- ProjectItem.Extender ("\<ProjectSubtypeName >") – これにより、カスタム メソッドの特定のオブジェクトを提供するプロジェクト サブタイプ<xref:EnvDTE.ProjectItem>プロジェクト内のオブジェクト。 プロジェクト サブタイプは、オートメーション エクステンダーを使用して、このオブジェクトを公開します。 <xref:EnvDTE80.IInternalExtenderProvider>メイン プロジェクト サブタイプ アグリゲーターで実装されるインターフェイスをそのオブジェクトを提供する必要があります、`VSHPROPID_ExtObjectCATID`から<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>(を目的に対応する`VSITEMID`) CATID。  
  
- Project.Properties – このコレクションは、の構成の独立したプロパティを公開、`Project`オブジェクト。 プロジェクトのプロパティの詳細については、次を参照してください。<xref:EnvDTE.Project.Properties%2A>します。 プロジェクト サブタイプは、オートメーション エクステンダーを使用して、そのプロパティをこのコレクションに追加します。 <xref:EnvDTE80.IInternalExtenderProvider>メイン プロジェクト サブタイプ アグリゲーターで実装されるインターフェイスをそのオブジェクトを提供する必要があります、 `VSHPROPID_BrowseObjectCATID` VSHPROPID2 から (に対応する、 `itemid` VSITEMID_ROOT の値から<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>) CATID。  
  
- Configuration.Properties – このコレクションは、特定の構成 (たとえば、デバッグなど) のプロジェクトの構成の依存プロパティを公開します。 詳細については、「<xref:EnvDTE.Configuration>」を参照してください。 プロジェクト サブタイプは、オートメーション エクステンダーを使用して、そのプロパティをこのコレクションに追加します。 <xref:EnvDTE80.IInternalExtenderProvider> CATID をメイン プロジェクト サブタイプ アグリゲーターで実装されるインターフェイスは、そのオブジェクトを提供`VSHPROPID_CfgBrowseObjectCATID`(に対応する、 `itemid` @property <xref:Microsoft.VisualStudio.VSConstants.VSITEMID>)。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject>インターフェイスが別の 1 つの構成の参照オブジェクトを区別するために使用されます。  
  
## <a name="see-also"></a>関連項目  
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>
