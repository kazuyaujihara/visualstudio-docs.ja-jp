---
title: 標準ドキュメントの保存 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], saving standard documents
- projects [Visual Studio SDK], saving standard documents
- persistence, saving standard documents
ms.assetid: d692fedf-b46e-4d60-84bd-578635042235
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: df93813d339a45689845b82fe4f5a185301b6c74
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72724099"
---
# <a name="saving-a-standard-document"></a>標準ドキュメントの保存
環境は、[保存]、[名前を付けて保存]、および [すべてを保存] コマンドを処理します。 ユーザーが **[ファイル]** メニューの **[保存]** 、名前を付け **[て保存]** 、または **[すべて]** 保存 を選択すると、**すべて保存**が行われるため、次のプロセスが実行されます。

 ![標準エディター](../../extensibility/internals/media/public.gif "Public")標準エディターのすべてのコマンド処理を保存、名前を付けて保存、および保存する

 このプロセスについては、次の手順で詳しく説明します。

1. 名前を付けて **[保存]** および **[名前を付けて保存]** コマンドを選択すると、環境では <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> サービスを使用して、アクティブなドキュメントウィンドウと、保存する必要がある項目を決定します。 アクティブなドキュメントウィンドウが判明すると、環境は、実行中のドキュメントテーブル内のドキュメントの階層ポインターと項目識別子 (itemID) を検索します。 詳細については、「 [Document Table の実行](../../extensibility/internals/running-document-table.md)」を参照してください。

    **[すべて保存]** コマンドを選択すると、実行中のドキュメントテーブルの情報を使用して、保存するすべての項目の一覧がコンパイルされます。

2. ソリューションは <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 呼び出しを受け取ると、選択された一連の項目 (つまり、<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> サービスによって公開される複数の選択項目) を反復処理します。

3. ソリューションでは、選択した項目ごとに、階層ポインターを使用して <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.IsItemDirty%2A> メソッドを呼び出し、 **[保存]** メニューコマンドを有効にする必要があるかどうかを判断します。 1つ以上の項目がダーティの場合、 **[保存]** コマンドが有効になります。 階層で標準エディターが使用されている場合、階層は、<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.IsDocDataDirty%2A> メソッドを呼び出すことによって、ダーティステータスのクエリをエディターに委任します。

4. 選択された各項目がダーティである場合、ソリューションは階層ポインターを使用して、適切な階層で <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.SaveItem%2A> メソッドを呼び出します。

    階層では、標準のエディターを使用してドキュメントを編集するのが一般的です。 この場合、そのエディターのドキュメントデータオブジェクトは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> インターフェイスをサポートする必要があります。 @No__t_0 メソッド呼び出しを受け取ると、ドキュメントデータオブジェクトの <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.SaveDocData%2A> メソッドを呼び出すことによって、ドキュメントが保存されていることをエディターに通知する必要があります。 エディターを使用すると、環境で **[名前を付けて保存]** ダイアログボックスを操作し、<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> インターフェイスに対して `Query Service` を呼び出すことができます。 これにより、<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> インターフェイスへのポインターが返されます。 次に、`pPersistFile` パラメーターを使って、エディターの <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> 実装へのポインターを渡すことによって、<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A> メソッドを呼び出す必要があります。 その後、環境で保存操作が実行され、エディターの **[名前を付けて保存]** ダイアログボックスが表示されます。 その後、環境では、<xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> を使用してエディターにコールバックします。

5. ユーザーが無題のドキュメント (つまり、以前に保存されていないドキュメント) を保存しようとすると、[名前を付けて保存] コマンドが実際に実行されます。

6. [名前を付けて保存] コマンドを実行すると、[名前を付けて保存] ダイアログボックスが表示され、ユーザーはファイル名を入力するように求められます。

    ファイルの名前が変更された場合、階層は <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetProperty%2A> (VSFPROPID_MkDocument) を呼び出すことによって、ドキュメントフレームのキャッシュされた情報を更新します。

   **[名前を付けて保存]** コマンドを使用してドキュメントの場所を移動し、階層がドキュメントの場所に依存している場合、階層は、開いているドキュメントウィンドウの所有権を別の階層に渡す役割を担います。 たとえば、プロジェクトによって、ファイルがプロジェクトに関連する内部または外部のファイル (その他のファイル) であるかどうかが追跡されている場合に発生します。 ファイルの所有権をその他のファイルプロジェクトに変更するには、次の手順に従います。

## <a name="changing-file-ownership"></a>ファイルの所有権の変更

#### <a name="to-change-file-ownership-to-the-miscellaneous-files-project"></a>ファイルの所有権をその他のファイルプロジェクトに変更するには

1. @No__t_0 インターフェイスのクエリサービス。

     @No__t_0 へのポインターが返されます。

2. @No__t_0 (`pszMkDocumentNew`, `punkWindowFrame`) メソッドを呼び出して、ドキュメントを新しい階層に転送します。 [名前を付けて保存] コマンドを実行する階層では、このメソッドを呼び出します。

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>
- [プロジェクト項目のオープンと保存](../../extensibility/internals/opening-and-saving-project-items.md)