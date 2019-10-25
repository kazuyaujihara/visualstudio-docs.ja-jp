---
title: カスタムドキュメントを保存する |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- persistence, saving custom documents
- projects [Visual Studio SDK], saving custom documents
- editors [Visual Studio SDK], saving custom documents
ms.assetid: 040b36d6-1f0a-4579-971c-40fbb46ade1d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cf67335b6a12b966eb148b3f8dcaf16339e2a29f
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72724084"
---
# <a name="saving-a-custom-document"></a>カスタム ドキュメントの保存
環境は、 **[保存]** 、名前を付け **[て保存]** 、および **[すべてを保存]** コマンドを処理します。 ユーザーが [**ファイル**の保存]、[名前を付け**て保存**]、**または [すべて**を保存]**をクリックする**と、すべて保存が行われるため、次のプロセスが実行されます。

 ![ユーザーエディターの保存](../../extensibility/internals/media/private.gif "Private")カスタムエディターのすべてのコマンド処理を保存、名前を付けて保存、および保存する

 このプロセスについては、次の手順で詳しく説明します。

1. [名前を付けて**保存**] コマンドと [名前を付け**て保存**] コマンドでは、<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> サービスを使用して、アクティブなドキュメントウィンドウと、どの項目を保存するかを決定します。 アクティブなドキュメントウィンドウが判明すると、環境は、実行中のドキュメントテーブル内のドキュメントの階層ポインターと項目識別子 (itemID) を検索します。 詳細については、「 [Document Table の実行](../../extensibility/internals/running-document-table.md)」を参照してください。

     [すべてを保存] コマンドの場合、環境は、実行中のドキュメントテーブルの情報を使用して、保存するすべての項目の一覧をコンパイルします。

2. ソリューションは <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 呼び出しを受け取ると、選択された一連の項目 (つまり、<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> サービスによって公開される複数の選択項目) を反復処理します。

3. ソリューションでは、選択した項目ごとに、階層ポインターを使用して <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.IsItemDirty%2A> メソッドを呼び出し、[保存] メニューコマンドを有効にする必要があるかどうかを判断します。 1つ以上の項目がダーティの場合、[保存] コマンドが有効になります。 階層で標準エディターが使用されている場合、階層は、<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.IsDocDataDirty%2A> メソッドを呼び出すことによって、ダーティステータスのクエリをエディターに委任します。

4. 選択された各項目がダーティである場合、ソリューションは階層ポインターを使用して、適切な階層で <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.SaveItem%2A> メソッドを呼び出します。

     カスタムエディターの場合、ドキュメントデータオブジェクトとプロジェクト間の通信はプライベートになります。 したがって、この2つのオブジェクトの間で、特別な永続化の問題が処理されます。

    > [!NOTE]
    > 独自の永続性を実装する場合は、必ず <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A> メソッドを呼び出して時間を節約してください。 このメソッドは、ファイルが安全に保存されていることを確認します (たとえば、ファイルが読み取り専用ではない)。

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>
- [プロジェクト項目のオープンと保存](../../extensibility/internals/opening-and-saving-project-items.md)