---
title: 新機能については、Visual Studio 2015 SDK のソースの管理 |Microsoft Docs
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- what's new [Visual Studio SDK], source control
- source control [Visual Studio SDK], what's new
ms.assetid: bcf85418-18fb-4824-9dae-d14bf3d56a77
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3b667a6c6322a925b49290ab3234788a4eee3544
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62856789"
---
# <a name="whats-new-in-source-control-for-the-visual-studio-2015-sdk"></a>新機能については、Visual Studio 2015 SDK のソース管理です。

[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]、ソース管理 VSPackage を実装して深く統合ソース制御ソリューションを提供することができます。 このセクションでは、ソース管理 Vspackage の機能について説明し、実装の手順の概要を説明します。

## <a name="the-source-control-vspackage"></a>ソース管理 VSPackage

Visual Studio では、ソース管理ソリューションの 2 つの種類をサポートします。 すべてのバージョンの Visual Studio では、統合することできますもソース管理プラグイン API ベース プラグイン。 深い統合、ソース管理 VSPackage を作成することもできます。[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]面の知識と自律性の高いレベルを必要とするソース管理ソリューションに適したパス。

VSPackage では、Visual Studio を機能のほとんどの種類を追加できます。 ソース管理 VSPackage では、ソース管理システムとのバック エンド通信をユーザーに表示される UI から、Visual Studio の完全なソース コントロールの機能を提供します。

ソース管理 VSPackage の実装には、「全部かゼロか」の戦略が必要です。 ソース管理 VSPackage の作成者とインターフェイスでさまざまなソース コントロールのインターフェイスと (ダイアログ ボックス、メニューのおよびツールバー) 全体のソース管理機能をカバーする、新しい UI 要素を実装する作業量が大幅に投資する必要があります。Visual Studio と正常に統合するすべてのパッケージの必要です。

次の手順では、ソース管理パッケージを実装するために必要なものの概要を提供します。 詳細については、次を参照してください。[ソース管理 VSPackage を作成する](../../extensibility/internals/creating-a-source-control-vspackage.md)します。

1. プライベート ソース管理サービスを proffers VSPackage を作成します。

2. Visual Studio によって提供される、ソース コントロールに関連するサービスで、インターフェイスを実装 (たとえば、<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>と<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider>インターフェイス)。

3. ソース管理 VSPackage を登録します。

4. すべてのソース管理メニュー項目、ダイアログ ボックス、ツールバー、およびコンテキスト メニューを含め、UI を実装します。

5. すべてのソース コントロールに関連するイベントは、それがアクティブであり、VSPackage によって処理する必要があるときに、ソース管理 VSackage に渡されます。

6. ソース管理 VSPackage が実装するようなイベントをリッスンする必要があります、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>トラック プロジェクト ドキュメント (TPD) のイベントとインターフェイス (によって実装される、<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>インターフェイス)、必要な操作をします。

## <a name="see-also"></a>関連項目

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>
- [概要](../../extensibility/internals/source-control-integration-overview.md)
- [ソース管理 VSPackage の作成](../../extensibility/internals/creating-a-source-control-vspackage.md)