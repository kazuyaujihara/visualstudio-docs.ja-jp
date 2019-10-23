---
title: 関連するサービスとインターフェイス (ソース管理 VSPackage) |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control packages, interfaces
- interfaces, source control packages
ms.assetid: 3e96e838-5675-46bb-99cf-40d420086038
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2ba041e1060f019e6b047fe4c589579112d690a9
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72724389"
---
# <a name="related-services-and-interfaces-source-control-vspackage"></a>関連サービスとインターフェイス (ソース管理 VSPackage)
このセクションでは、[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 内のすべてのソース管理 VSPackage に関連するインターフェイスの一覧を示します。 ソース管理 VSPackage は、これらのインターフェイスの一部を実装し、他のインターフェイスを使用してソース管理タスクを実行します。

## <a name="interfaces-implemented-by-and-for-source-control-vspackages"></a>およびによって実装された、ソース管理 Vspackage のインターフェイス
 次のインターフェイスは [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] に記述されており、ソース管理 VSPackage は、必要な機能セットに応じてそれらのサブセットを実装します。 一部のインターフェイスは必須としてマークされており、すべてのソース管理 VSPackage によって実装される必要があります。

 パッケージが実装していないインターフェイスの場合、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 既定の実装が提供されます。 既定の実装は、VSPackage が登録されておらず、プロジェクトが制御されていない場合に備えて設計されていることに注意してください。 適切に記述されたソース管理 VSPackage は、これらのインターフェイスの既定の実装に残すのではなく、必要なすべてのインターフェイスを実装します。

 ソース管理 VSPackage は、次のインターフェイスの一部またはすべてをカプセル化するプライベートサービスを実装する必要があります。

 インターフェイスは次のとおりです。

- 必須: 適切なエンティティ (ソース管理 VSPackage、ソース管理スタブ、プロジェクト) は、インターフェイスを実装する必要があります。

- 推奨: エンティティは、このインターフェイスを実装する必要があります。それ以外の場合は、ソース管理機能が制限されることがあります。

- 省略可能: エンティティはこのインターフェイスを実装して、より豊富な機能セットを提供できます。

| Interface | 目的 | 実装 | 導入? |
| - | - |--------------------------|-------------|
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> | エディターは、ファイルを変更または保存する前に、このインターフェイスを呼び出します。 ソース管理 VSPackage は、チェックアウトに失敗した場合にファイルをチェックアウトしたり、操作を拒否したりできます。 | ソース管理 VSPackage | 推奨 |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2> | このインターフェイスは、プロジェクトの基本的なソース管理機能を提供します。たとえば、ソース管理を使用したプロジェクトの登録と登録解除や、基本的なソース管理のグリフのサポートなどを行うことができます。 | ソース管理 VSPackage | 必要 |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2> | このインターフェイスは、<xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> 関数を使用するか、`IVsHierarchy` を実装するオブジェクトを `IVsSccProject2` にキャストするだけで、<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> から取得されます。 プロジェクトのソース管理下にあるファイルを取得したり、現在のソース管理の状態または場所をプロジェクトに通知したりするために使用されます。 | [プロジェクト] | 必要 |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider> | 統合モジュールは、このインターフェイスを使用して、現在のアクティブな VSPackage を設定します。 | ソース管理 VSPackage | 必要 |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> | このインターフェイスは、サブスクリプションモデルに基づいています。 VSPackage は、ドキュメントイベントを受信しようとしていることを通知し、発生しようとしているイベントについてシェルで通知することができます。 @No__t_0 によって実装および処理され、`IVsTrackProjectDocumentsEvents2` を実装するイベントを VSPackage に渡します。 | ソース管理スタブ | 必要 |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments3> | このインターフェイスは、バッチ処理、同期された読み取り/書き込み操作、および高度な `OnQueryAddFiles` 方法を提供します。 | ソース管理スタブ | 必要 |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2> | **ソリューションエクスプローラー**とプロジェクトは、新しいファイルがプロジェクトに追加されたとき、またはファイルやフォルダーの名前が変更されたり、プロジェクトから削除されたりすると、このインターフェイスを呼び出します。 ソース管理 VSPackage は、プロジェクトファイルをチェックアウトするか、操作を取り消すことができます。 | ソース管理 VSPackage | 推奨 |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents3> | **ソリューションエクスプローラー**およびプロジェクトは、IVstrackProjectDocuments3 インターフェイスのメソッドに対する呼び出しに応答してこのインターフェイスを呼び出します。 ソース管理 VSPackage は、バッチ処理された操作、同期された読み取り/書き込み操作を追跡し、より高度な `OnQueryAddFiles` メソッドを操作できます。 | ソース管理 VSPackage | 推奨 |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccEnlistmentPathTranslation> | このインターフェイスは、Web プロジェクトの参加管理サポートを提供します。 | ソース管理 VSPackage | 推奨 |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManagerTooltip> | このインターフェイスは、プロジェクト内のソース管理ファイルのツールヒントを取得するために使用されます。 | ソース管理 VSPackage | Optional |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccOpenFromSourceControl> | このインターフェイスは、名前空間拡張のサポートを提供します。 | ソース管理 VSPackage | Optional |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccControlNewSolution> | VSPackage は、このインターフェイスを使用して、名前空間の拡張機能を **[新規]** 、 **[開く**]、 **[保存]** の各ダイアログボックスに統合します。 その結果、プロジェクトは、作成時にソース管理に自動的に追加されたり、保存操作が有効になったときにソース管理に追加されたりすることができます。 | ソース管理 VSPackage | Optional |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs> | VSPackage は、このインターフェイスを使用して、**ソリューションエクスプローラー**のノードのソース管理のグリフとして追加のグリフを定義します。 | ソース管理 VSPackage | Optional |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccAddWebProjectFromSourceControl> | Web プロジェクトの **[追加]** ダイアログボックスでは、このインターフェイスを使用します。 ソース管理の場所を参照したり、その場所にあるソース管理リポジトリに以前に追加された Web プロジェクトを開いたりするためのメソッドが用意されています。 | ソース管理 VSPackage | 推奨 |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromScc> | このインターフェイスでは、ソース管理からのプロジェクトの非同期 (バックグラウンド) 読み込みがサポートされています。 | ソース管理 VSPackage | Optional |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromSccProjectEvents> | このインターフェイスにより、プロジェクトは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromScc> によって開始された非同期読み込みの進行状況を監視できます。 | [プロジェクト] | Optional |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccToolsOptions> | このインターフェイスを使用すると、IDE はアクティブなソース管理 VSPackage に対してクエリを実行できます。 IDE は、アクティブなソース管理 VSPackage が登録されていない場合でも、意味のあるソース管理設定の値を照会します。 このインターフェイスは [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] によって実装および処理されます。 | ソース管理スタブ | 必要 |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider> | このインターフェイスは、ソース管理 VSPackage の登録に使用されます。 | ソース管理スタブ | 必要 |
| <xref:EnvDTE.SourceControl> | このインターフェイスは、オートメーションで使用されます。 そのため、UI を表示せずに実行できる関数のみが公開されます。 | ソース管理 VSPackage | Optional |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps> | このインターフェイスは、ソース管理の設定をソリューション (.sln) ファイルに保存するために使用されます。 設定には、ソース管理の場所とソース管理の状態フラグが含まれます。 | ソース管理 VSPackage | 推奨 |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts> | このインターフェイスは、ソース管理の設定をソリューションオプション (.suo) ファイルに保存するために使用されます。 これには、現在のユーザーの参加場所など、ユーザー固有のソース管理設定が含まれる場合があります。 | ソース管理 VSPackage | 推奨 |
| <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3> | このインターフェイスは、ソリューションを閉じる前にプロジェクトファイルのチェックイン、プロジェクトを開くときにソース管理から新しいファイルを取得するなどの操作を実行するために、イベントを監視するために使用されます。 | ソース管理 VSPackage | 推奨 |

## <a name="see-also"></a>関連項目
- [デザイン要素](../../extensibility/internals/source-control-vspackage-design-elements.md)