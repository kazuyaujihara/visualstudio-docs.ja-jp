---
title: Document Table | を実行していますMicrosoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- read locks
- running document table (RDT), IVsDocumentLockHolder interface
- running document table (RDT)
- running document table (RDT), edit locks
- document data objects, running document table
ms.assetid: bbec74f3-dd8e-48ad-99c1-2df503c15f5a
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4645899e8c4cd73758316a3c2a8d74ccb169aa2d
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72724067"
---
# <a name="running-document-table"></a>ドキュメント テーブルの実行
IDE では、現在開いているすべてのドキュメントの一覧が、実行中のドキュメントテーブル (RDT) と呼ばれる内部構造で保持されます。 この一覧には、これらのドキュメントが現在編集されているかどうかに関係なく、メモリ内のすべての開いているドキュメントが含まれます。 ドキュメントは、プロジェクトまたはメインプロジェクトファイル (.vcxproj ファイルなど) 内のファイルを含む、永続化された任意の項目です。

## <a name="elements-of-the-running-document-table"></a>実行中のドキュメントテーブルの要素
 実行中のドキュメントテーブルには、次のエントリが含まれています。

|要素|説明|
|-------------|-----------------|
|ドキュメントモニカー|ドキュメントデータオブジェクトを一意に識別する文字列。 これは、ファイルを管理するプロジェクトシステムの絶対ファイルパスです (たとえば、C:\MyProject\MyFile)。 この文字列は、データベース内のストアドプロシージャなど、ファイルシステム以外のストアに保存されたプロジェクトにも使用されます。 この場合、プロジェクトシステムは、ドキュメントを格納する方法を決定するために認識して解析できる一意の文字列を指定できます。|
|階層の所有者|@No__t_0 インターフェイスによって表される、ドキュメントを所有する階層オブジェクト。|
|項目 ID|階層内の特定の項目の項目識別子。 この値は、このドキュメントを所有する階層内のすべてのドキュメント間で一意ですが、この値は異なる階層間で一意であるとは限りません。|
|ドキュメントデータオブジェクト|少なくとも、これは `IUnknown`<br /><br /> オブジェクト。 IDE では、カスタムエディターのドキュメントデータオブジェクトの `IUnknown` インターフェイスを超える特定のインターフェイスは必要ありません。 ただし、標準のエディターでは、プロジェクトからのファイルの永続化呼び出しを処理するために、エディターの <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> インターフェイスの実装が必要です。 詳細については、「[標準ドキュメントの保存](../../extensibility/internals/saving-a-standard-document.md)」を参照してください。|
|フラグ|ドキュメントを保存するかどうかを制御するフラグ (読み取りロックまたは編集ロックを適用するかどうかなど) は、RDT にエントリを追加するときに指定できます。 詳細については、<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> 列挙型のページをご覧ください。|
|ロック数の編集|編集ロックの数。 編集ロックは、一部のエディターでドキュメントが編集用に開かれていることを示します。 編集ロックの数が0に遷移すると、ドキュメントが変更されている場合は、保存するように求められます。 たとえば、 **[新しいウィンドウ]** コマンドを使用してエディターでドキュメントを開くたびに、rdt にそのドキュメントの編集ロックが追加されます。 編集ロックを設定するには、ドキュメントに階層または項目 ID が必要です。|
|読み取りロック数|読み取りロックの数。 読み取りロックは、ドキュメントがウィザードなどの何らかのメカニズムによって読み取られていることを示します。 読み取りロックは、ドキュメントを編集できないことを示すために、RDT でドキュメントを保持します。 ドキュメントに階層または項目 ID がない場合でも、読み取りロックを設定できます。 この機能を使用すると、メモリ内のドキュメントを開いて、ドキュメントが階層によって所有されていなくても、RDT に入力できます。 この機能はほとんど使用されません。|
|ロックホルダー|@No__t_0 インターフェイスのインスタンス。 ロックホルダーは、エディター以外でドキュメントを開いたり編集したりするためのウィザードなどの機能によって実装されます。 ロックの所有者は、編集ロックを文書に追加して、編集中のドキュメントが閉じられるのを防ぐことができます。 通常、編集ロックは、ドキュメントウィンドウ (つまり、エディター) によってのみ追加されます。|

 RDT 内の各エントリには、一意の階層または項目 ID が関連付けられています。これは、通常、プロジェクト内の1つのノードに対応しています。 編集に使用できるすべてのドキュメントは、通常、階層によって所有されます。 RDT で作成されたエントリは、どの階層が、現在編集中のドキュメントデータオブジェクトを所有しているかをより正確に制御します。 IDE では、RDT の情報を使用して、一度に複数のプロジェクトによってドキュメントが開かれないようにすることができます。

 階層では、データの永続性も制御され、RDT の情報を使用して **[保存]** ダイアログボックスと **[名前を付けて保存]** ダイアログボックスが更新されます。 ユーザーがドキュメントを変更した後、 **[ファイル]** メニューから **[終了]** コマンドを選択すると、 **[変更の保存]** ダイアログボックスが表示され、現在変更されているすべてのプロジェクトとプロジェクト項目が表示されます。 これにより、ユーザーは保存するドキュメントを選択できます。 保存するドキュメントの一覧 (変更されたドキュメント) は、RDT から生成されます。 アプリケーションの終了時に **[変更の保存]** ダイアログボックスに表示されるはずの項目には、rdt のレコードが含まれている必要があります。 RDT では、保存されるドキュメントと、各ドキュメントの Flags エントリに指定された値を使用して保存操作についてユーザーに確認を求めるかどうかを調整します。 RDT フラグの詳細については、<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> 列挙体を参照してください。

## <a name="edit-locks-and-read-locks"></a>ロックと読み取りロックの編集
 Edit locks と read locks は RDT に存在します。 ドキュメントウィンドウは、編集ロックを増減します。 このため、ユーザーが新しいドキュメントウィンドウを開くと、編集ロックカウントは1ずつ増加します。 編集ロックの数が0になると、階層は、関連付けられているドキュメントのデータを永続化または保存するように通知されます。 階層では、ファイルとして永続化したり、リポジトリ内の項目として保持するなど、任意の方法でデータを永続化することができます。 @No__t_1 インターフェイスの <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.LockDocument%2A> メソッドを使用して、編集ロックと読み取りロックを追加したり、<xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnlockDocument%2A> メソッドを使用してこれらのロックを解除したりできます。

 通常、エディターのドキュメントウィンドウがインスタンス化されると、ウィンドウフレームによって、RDT 内のドキュメントの編集ロックが自動的に追加されます。 ただし、標準のドキュメントウィンドウを使用しない (つまり、<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> インターフェイスを実装しない) ドキュメントのカスタムビューを作成する場合は、独自の編集ロックを設定する必要があります。 たとえば、ウィザードでは、エディターで開かずにドキュメントが編集されます。 ウィザードと同様のエンティティによってドキュメントロックが開かれるようにするには、これらのエンティティが <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> インターフェイスを実装する必要があります。 ドキュメントのロックホルダーを登録するには、<xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.RegisterDocumentLockHolder%2A> メソッドを呼び出し、<xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> の実装を渡します。 これにより、ドキュメントのロックホルダーが RDT に追加されます。 ドキュメントロックホルダーを実装するもう1つのシナリオは、特別なツールウィンドウでドキュメントを開く場合です。 このインスタンスでは、ツールウィンドウでドキュメントを閉じることはできません。 ただし、RDT でドキュメントのロックの所有者として登録することにより、<xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder.CloseDocumentHolder%2A> メソッドの実装を呼び出して、ドキュメントを閉じるように求めることができます。

## <a name="other-uses-of-the-running-document-table"></a>実行中のドキュメントテーブルのその他の使用
 IDE 内の他のエンティティは、RDT を使用してドキュメントに関する情報を取得します。 たとえば、ソース管理マネージャーは RDT を使用して、ファイルの最新バージョンを取得した後に、エディターでドキュメントを再読み込みするようにシステムに指示します。 これを行うには、ソース管理マネージャーが RDT 内のファイルを検索して、いずれかが開いているかどうかを確認します。 指定されている場合、ソース管理マネージャーはまず、階層が <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> メソッドを実装していることを確認します。 プロジェクトに <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> メソッドが実装されていない場合、ソース管理マネージャーは、ドキュメントデータオブジェクトの <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.ReloadDocData%2A> メソッドの実装を直接確認します。

 また、ユーザーがドキュメントを要求した場合、IDE は RDT を使用して開いているドキュメントを resurface (前面に移動) します。 詳細については、「[[ファイルを開く] コマンドを使用したファイルの表示](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)」を参照してください。 ファイルが RDT で開かれているかどうかを確認するには、次のいずれかの操作を行います。

- ドキュメントモニカー (つまり、完全なドキュメントパス) を照会して、アイテムが開いているかどうかを確認します。

- 階層または項目 ID を使用して、プロジェクトシステムに完全なドキュメントパスを要求してから、RDT で項目を確認します。

## <a name="see-also"></a>関連項目
- [RDT_ReadLock の使用法](../../extensibility/internals/rdt-readlock-usage.md)
- [ドキュメント テーブルの保存と実行](../../extensibility/internals/persistence-and-the-running-document-table.md)