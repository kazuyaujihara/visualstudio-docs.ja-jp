---
title: ソース管理の構成の詳細 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], configuration details
ms.assetid: adbee9fc-7a2e-4abe-a3b8-e6615bcd797f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0a6c51dfe4ad9378af04da61dbd7e9011c4678f1
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72723790"
---
# <a name="source-control-configuration-details"></a>ソース管理構成の詳細
ソース管理を実装するには、次の操作を行うためにプロジェクトシステムまたはエディターを適切に構成する必要があります。

- 変更された状態に移行するためのアクセス許可を要求する

- ファイルを保存するためのアクセス許可を要求する

- プロジェクト内のファイルを追加、削除、または名前変更するためのアクセス許可を要求する

## <a name="request-permission-to-transition-to-changed-state"></a>変更された状態に移行するためのアクセス許可を要求する
 プロジェクトまたはエディターは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> を呼び出すことによって変更された (ダーティ) 状態に移行するためのアクセス許可を要求する必要があります。 @No__t_0 を実装する各エディターは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData.IsDocDataDirty%2A> の `True` を返す前に、<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> を呼び出し、承認を受けて、環境からドキュメントを変更する必要があります。 プロジェクトは基本的にはプロジェクトファイルのエディターであり、そのため、ファイルのテキストエディターと同じように、プロジェクトファイルに対して変更された状態の追跡を実装する責任があります。 環境は、変更されたソリューションの状態を処理しますが、プロジェクトファイルやその項目など、ソリューションが参照しているオブジェクトの変更された状態を処理する必要があります。 一般に、プロジェクトまたはエディターが項目の永続化を管理する必要がある場合は、変更された状態の追跡を実装する必要があります。

 @No__t_0 の呼び出しに応答して、環境は次のことを実行できます。

- 変更への呼び出しを拒否します。その場合、エディターまたはプロジェクトは変更なし (クリーン) 状態のままにしておく必要があります。

- ドキュメントデータを再度読み込む必要があることを示します。 プロジェクトの場合、環境によってプロジェクトのデータが再読み込みされます。 エディターは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.ReloadDocData%2A> の実装を通じてディスクからデータを再読み込みする必要があります。 どちらの場合も、データが再読み込みされると、プロジェクトまたはエディターのコンテキストが変更される可能性があります。

  これは、適切な `IVsQueryEditQuerySave2::QueryEditFiles` 呼び出しを既存のコードベースにカルチャだけする複雑で困難なタスクです。 そのため、これらの呼び出しは、プロジェクトまたはエディターの作成中に統合する必要があります。

## <a name="request-permission-to-save-a-file"></a>ファイルを保存するためのアクセス許可を要求する
 プロジェクトまたはエディターがファイルを保存する前に、<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A> または <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A> を呼び出す必要があります。 プロジェクトファイルの場合、これらの呼び出しは、プロジェクトファイルを保存するタイミングを認識するソリューションによって自動的に完了します。 @No__t_0 のエディター実装がヘルパー関数 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A> を使用する場合を除き、これらの呼び出しを行うのはエディターの役割です。 エディターがこの方法で `IVsPersistDocData2` を実装している場合は、`IVsQueryEditQuerySave2::QuerySaveFile` または `IVsQueryEditQuerySave2::QuerySaveFiles` の呼び出しが行われます。

> [!NOTE]
> 常にこれらの呼び出しを事前ににします。つまり、エディターがキャンセルを受け取ることができるようになります。

## <a name="request-permission-to-add-remove-or-rename-files-in-the-project"></a>プロジェクト内のファイルを追加、削除、または名前変更するためのアクセス許可を要求する
 プロジェクトがファイルまたはディレクトリを追加、名前変更、または削除できるようにするには、その前に、適切な `IVsTrackProjectDocuments2::OnQuery*` メソッドを呼び出して、環境からアクセス許可を要求する必要があります。 アクセス許可が付与されている場合は、プロジェクトで操作を完了し、適切な `IVsTrackProjectDocuments2::OnAfter*` メソッドを呼び出して、操作が完了したことを環境に通知する必要があります。 プロジェクトは、親ファイルだけでなく、すべてのファイル (たとえば、特殊ファイル) に対して <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> インターフェイスのメソッドを呼び出す必要があります。 ファイル呼び出しは必須ですが、ディレクトリ呼び出しは省略可能です。 プロジェクトにディレクトリ情報が含まれている場合は、適切な <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> メソッドを呼び出す必要がありますが、この情報がない場合は、環境によってディレクトリ情報が推測されます。

 プロジェクトが open または close で `IVsTrackProjectDocuments2` のメソッドを呼び出すことはできません。 起動時にこの情報を必要とするリスナーは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenSolution%2A> イベントを待機し、ソリューションを反復処理して必要な情報を見つけることができます。 シャットダウン時に、この情報は必要ありません。 `IVsTrackProjectDocuments2` は <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments> から提供されます。

 追加、名前の変更、および削除の各操作について、`OnQuery*` メソッドと `OnAfter*` メソッドがあります。 @No__t_0 メソッドを呼び出して、ファイルまたはディレクトリを追加、名前変更、または削除するアクセス許可を要求します。 ファイルまたはディレクトリが追加、名前変更、または削除され、プロジェクトの状態が新しい状態を反映した後に、`OnAfter*` メソッドを呼び出します。

## <a name="see-also"></a>関連項目

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>
- [ソース管理のサポート](../../extensibility/internals/supporting-source-control.md)