---
title: ソース管理 VSPackage Architecture |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control packages, architecture
ms.assetid: 453125fc-23dc-49b1-8476-94581f05e6c7
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9484aabd0080b0a44d75a8a5f6d90d9217d74b8e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72723349"
---
# <a name="source-control-vspackage-architecture"></a>ソース管理 VSPackage アーキテクチャ
ソース管理パッケージは、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE によって提供されるサービスを使用する VSPackage です。 戻り値として、ソース管理パッケージの機能がソース管理サービスとして提供されます。 また、ソース管理パッケージは、ソース管理を [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] に統合するためのソース管理プラグインよりも汎用性があります。

 ソース管理プラグイン API を実装するソース管理プラグインは、厳密なコントラクトに準拠しています。 たとえば、既定の [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ユーザーインターフェイス (UI) をプラグインで置き換えることはできません。 さらに、ソース管理プラグイン API では、プラグインが独自のソース管理モデルを実装することはできません。 ただし、ソース管理パッケージでは、これらの両方の制限が解消します。 ソース管理パッケージは、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ユーザーのソース管理エクスペリエンスを完全に制御できます。 さらに、ソース管理パッケージは、独自のソース管理モデルとロジックを使用して、ソース管理に関連するすべてのユーザーインターフェイスを定義できます。

## <a name="source-control-package-components"></a>ソース管理パッケージのコンポーネント
 アーキテクチャ図に示されているように、ソース管理スタブという名前の [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] コンポーネントは、ソース管理パッケージと [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] を統合する VSPackage です。

 ソース管理スタブは、次のタスクを処理します。

- ソース管理のパッケージ登録に必要な共通の UI を提供します。

- ソース管理パッケージを読み込みます。

- ソース管理パッケージをアクティブ/非アクティブとして設定します。

  ソース管理スタブは、ソース管理パッケージのアクティブなサービスを検索し、IDE からのすべての受信サービス呼び出しをそのパッケージにルーティングします。

  ソース管理アダプターパッケージは、によって提供さ [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 特別なソース管理パッケージです。 このパッケージは、ソース管理プラグイン API に基づいたソース管理プラグインをサポートするための中心的なコンポーネントです。 ソース管理プラグインがアクティブプラグインの場合、ソース管理スタブはそのイベントをソース管理アダプターパッケージに送信します。 さらに、ソース管理アダプターパッケージは、ソース管理プラグイン API を使用してソース管理プラグインと通信します。また、すべてのソース管理プラグインに共通の既定の UI も提供します。

  一方、ソース管理パッケージがアクティブパッケージの場合、ソース管理スタブは、[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] ソース管理パッケージインターフェイスを使用して、パッケージと直接通信します。 ソース管理パッケージは、独自のソース管理 UI をホストします。

  ![ソース管理アーキテクチャのグラフィック](../../extensibility/internals/media/vsipsccarch.gif "VSIPSCCArch")

  ソース管理パッケージの場合、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] は統合のためのソース管理コードまたは API を提供しません。 これは、「ソース管理プラグインの[作成](../../extensibility/internals/creating-a-source-control-plug-in.md)」で説明されている方法と同じです。ソース管理プラグインは、厳密な一連の関数とコールバックを実装する必要があります。

  VSPackage と同様に、ソース管理パッケージは `CoCreateInstance` を使用して作成できる COM オブジェクトです。 VSPackage を使用すると、<xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> を実装することによって [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE でそれ自体を使用できるようになります。 インスタンスが作成されると、VSPackage は、IDE 内の使用可能なサービスとインターフェイスへの VSPackage アクセスを提供するサイトポインターと <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> インターフェイスを受け取ります。

  VSPackage ベースのソース管理パッケージを作成するには、ソース管理プラグイン API ベースのプラグインを記述するよりも高度なプログラミングの専門知識が必要です。

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>
- [はじめに](../../extensibility/internals/getting-started-with-source-control-vspackages.md)