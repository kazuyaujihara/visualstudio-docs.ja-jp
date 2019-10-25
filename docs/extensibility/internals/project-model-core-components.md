---
title: プロジェクトモデルコアコンポーネント |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project models, objects and interfaces
- project models, services
ms.assetid: b2f572d3-b26d-4846-92d1-84055fac141a
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4e84438aa57492e28c4e8debc8c1c54e5f496eae
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72725726"
---
# <a name="project-model-core-components"></a>プロジェクト モデルのコア コンポーネント
次の表は、プロジェクトモデルで拡張されています。 この表では、モデルで識別されるインターフェイスとサービス、および特定のオブジェクトに関連付けられているインターフェイスとサービスについて簡単に説明します。 また、特定のプロジェクトの種類の要件に応じて、プロジェクトの作成とメンテナンスでオプションとなる他のインターフェイスの詳細も示します。

 詳細については、「[シンボル参照ツールのサポート](../../extensibility/internals/supporting-symbol-browsing-tools.md)」を参照してください。

### <a name="package-object"></a>パッケージオブジェクト

|Interface|コメント|
|---------------|--------------|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>|IDE で VSPackage を初期化し、そのサービスを IDE で使用できるようにします。|

### <a name="project-factory-object"></a>プロジェクトファクトリオブジェクト

|Interface|コメント|
|---------------|--------------|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>|新しいプロジェクトの作成と、既存のプロジェクトのオープンを管理します。|

### <a name="project-objects"></a>プロジェクトオブジェクト

|インターフェイス|コメント|
|----------------|--------------|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>|プロジェクト項目の追加と削除を管理し、エディターを開き、各ドキュメントモニカーと `VSITEMID` 間のマッピングを保持します。 @No__t_0 および `IVsProject2` から継承されます。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>|ナビゲーションと表示のプロパティを管理し、イベントを提供します。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>|切り取りや名前の変更など、フォーカスがソリューションエクスプローラーにある場合にのみ適用されるコマンドに対して、`IOleCommandTarget` と同様にコマンドを実行できるようにします。|
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|プロジェクト階層の主要なコマンドターゲットインターフェイスとして機能します。 これは、オブジェクトに対してコマンドの状態または状態のクエリを実行し、コマンドを実行するための標準インターフェイスです。 プロジェクトウィンドウでフォーカスされていない場合に使用できます。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>|プロジェクトの状態の永続性を調整します。 通常、プロジェクトの状態はプロジェクトファイルとして保存されますが、ファイルベースではない記憶域システムに適応させることができます。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2>|プロジェクトが、ディスク上のファイルまたは他のストレージシステム内のオブジェクトとして、プロジェクト項目の永続化のすべての側面を管理できるようにします。 @No__t_0 インターフェイスは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> インターフェイスを実装しない項目に使用されます。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|ソースコード管理との相互作用を調整します。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfgProvider>|プロジェクトで構成情報を管理できるようにします。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2>|デバッグ/リリース構成などのプロジェクト構成オブジェクトを管理します。 ビルド、配置、およびデバッグの各操作は、プロジェクト構成オブジェクトを使用して調整されます。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDeleteHandler>|階層項目の削除 (破壊) オプションまたは削除 (非破壊的) オプションを制御するために、階層によって実装されます。 @No__t_1 インターフェイスから `IVsHierarchyDeleteHandler` インターフェイスでクエリインターフェイスを呼び出します。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsGetCfgProvider>|@No__t_1 インターフェイスを実装するプロジェクトオブジェクトとは異なる COM id で、`IVsCfgProvider2` インターフェイスをサポートするオブジェクトを持つ実装オプションを提供します。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectStartupServices>|他の開発者がプロジェクトを拡張できるように実装された省略可能なインターフェイス。 @No__t_0 インターフェイスを使用すると、サードパーティの VSPackage はプロジェクトファイルに保持されている GUID を登録して、プロジェクトが読み込まれるたびに、サードパーティのサービス GUID をプロジェクトファイルに読み込み、その GUID の `QueryService` を呼び出すことができるようにします。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierWinClipboardHelperEvents>|切り取り、コピー、貼り付けなどのクリップボード操作を調整するために、ソース階層によって `UIHierarchy` ウィンドウに実装されます。 @No__t_0 インターフェイスを使用して、クリップボードイベントを登録します。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDropDataSource2>|UI 階層ウィンドウでのドラッグアンドドロップ操作中に、データソースに対して相対的にドラッグされた項目に関する情報を提供します。 @No__t_0 インターフェイスから呼び出されます。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDropDataTarget>|UI 階層ウィンドウでのドラッグアンドドロップ操作中に、ドロップ先に対してドラッグした項目に関する情報を提供します。 @No__t_0 インターフェイスから呼び出されます。|

### <a name="configuration-object"></a>構成オブジェクト

|インターフェイス|コメント|
|----------------|--------------|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg>|構成に関する情報を提供します。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2>|プロジェクトで構成情報を管理できるようにします。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>|デバッガーの制御下でプロジェクトを実行できるようにします。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg>|他のプロジェクトの配置操作を実行する配置プロジェクトによって実装されます。|

### <a name="configuration-builder-object"></a>構成ビルダーオブジェクト

|インターフェイス|コメント|
|----------------|--------------|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg>|プロジェクト構成のビルド操作を管理します。|

### <a name="additional-project-objects"></a>追加のプロジェクトオブジェクト

|インターフェイス|コメント|
|----------------|--------------|
|`IDispatch`<br /><br /> <xref:Microsoft.VisualStudio.OLE.Interop.ISpecifyPropertyPages>|項目のプロパティを **[プロパティ]** ウィンドウに表示します。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput2><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumOutputs>|配置の出力を表示します。|

 次の表に、プロジェクトモデルで識別されるサービスの簡単な説明を示します。

### <a name="services"></a>Services

|[サービス]|コメント|
|-------------|--------------|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterProjectTypes>|プロジェクトファクトリが IDE に存在することを登録するプロジェクトの種類を実装する Vspackage によって使用されます。 @No__t_1 メソッドが呼び出されたときに、VSPackage がこのサービスの `QueryService` を呼び出し、プロジェクトファクトリを登録する必要があります。 @No__t_0 メソッドが呼び出されていない場合、プロジェクトはインスタンス化されません。|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>|プロジェクトの列挙、新しいプロジェクトの作成、プロジェクトの変更の通知など、現在のソリューションに組み込まれている組み込みの概念にアクセスできるようにします。|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>|ソース管理に参加する必要があるプロジェクトによって呼び出されます。|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>|開いているドキュメントのテーブルを保持し、1つ以上のプロジェクト項目が既に開かれているかどうかを確認します。|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShellOpenDocument>|標準エディターまたは特定のエディターを使用してプロジェクト項目を実際に開くために呼び出されるインターフェイスとメソッドを含みます。|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>|項目を追加、削除、または名前変更するときに、すべてのプロジェクトによって呼び出される必要があります。|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFileChangeEx>|ファイルまたはディレクトリへの変更を管理し、選択したファイルがディスク上で変更されたことをクライアントに通知します。|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>|項目をダーティにしたり保存したりする前に、すべてのプロジェクトとエディターによって呼び出される必要があります。|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolutionBuildManager>|プロジェクト構成のビルドおよび配置操作の順序を管理します。|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellDebugger>|ほとんどのデバッグコントロールに使用される低レベルのデバッガーサービスへのアクセスを提供します。|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>|現在選択されている情報への Vspackage アクセスを有効にし、 **[プロパティ]** ウィンドウとの通信を有効にします。|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>|ツールウィンドウまたはドキュメントウィンドウを作成および列挙する機能や、ユーザーにエラーを報告する機能など、UI に関連する基本的な IDE 機能を提供します。|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar>|IDE のステータスバーへのアクセスを提供します。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibility3>|オートメーションモデルを実装するために使用されます。 プロジェクトモデルでは、オブジェクトのインスタンスを作成できるプロパティオブジェクトが返されます。|
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIHierWinClipboardHelper>|階層内のプロジェクトオブジェクトにクリップボードイベントを実装するために使用されます。 `SVsUIHierWinClipboardHelper` を使用すると、切り取り、コピー、貼り付けの各操作を正しく処理できます。|

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>
- [チェック リスト: 新しいプロジェクト タイプの作成](../../extensibility/internals/checklist-creating-new-project-types.md)
- [ビルド内にありません: HierUtil7 プロジェクトクラスを使用したC++プロジェクトの種類の実装 ()](https://msdn.microsoft.com/library/a5c16a09-94a2-46ef-87b5-35b815e2f346)
- [シンボル参照ツールのサポート](../../extensibility/internals/supporting-symbol-browsing-tools.md)
- [プロジェクト モデルの要素](../../extensibility/internals/elements-of-a-project-model.md)