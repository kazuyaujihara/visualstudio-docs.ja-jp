---
title: RDT_ReadLock の使用法 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- RDT_ReadLock
- visible
- RDT_EditLock
- invisible
ms.assetid: b935fc82-9d6b-4a8d-9b70-e9a5c5ad4a55
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 04997bfed66da015c4aef82f4741218c88b9ecd1
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335032"
---
# <a name="rdtreadlock-usage"></a>RDT_ReadLock の使用法

[_VSRDTFLAGS します。RDT_ReadLock](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS.RDT_ReadLock>)これは、Visual Studio IDE で現在開いているすべてのドキュメントの一覧で、実行されているドキュメント テーブル (RDT)、ドキュメントをロックするためのロジックを提供するフラグです。 このフラグは、ドキュメントが開かれた文書は、ユーザー インターフェイスに表示されるか、メモリの目に見えない形で保持されているかどうかを判断します。

一般を使用する[_VSRDTFLAGS します。RDT_ReadLock](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS.RDT_ReadLock>)次のいずれかが true の場合。

- ドキュメントを視覚的にオープンする読み取り専用とはまだが確立されていることが、<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>所有する必要があります。

- 場合、ユーザーが、ユーザーが、UI に表示されることと、終了しようとし、前にない開かれた視覚的ドキュメントを保存するように求められます。

## <a name="how-to-manage-visible-and-invisible-documents"></a>表示と非表示のドキュメントを管理する方法

ユーザーが UI では、ドキュメントを開いたときに、<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>ドキュメントの所有者を確立する必要があります、 [_VSRDTFLAGS します。RDT_EditLock](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS.RDT_EditLock>)フラグを設定する必要があります。 ない場合は<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>所有者が確立されると、その後、ユーザーがクリックしたときに、ドキュメントは保存されません**すべて保存**または IDE を終了します。 かどうか、ドキュメントが開いていない視覚的、メモリ内で変更されていて、ユーザーがシャット ダウン時にドキュメントを保存するように求めまたは保存つまり**すべて保存**を選択した場合、`RDT_ReadLock`は使用できません。 代わりに、使用する必要があります、`RDT_EditLock`を登録し、<xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder>ときに、 [__VSREGDOCLOCKHOLDER します。RDLH_WeakLockHolder](<xref:Microsoft.VisualStudio.Shell.Interop.__VSREGDOCLOCKHOLDER.RDLH_WeakLockHolder>)フラグ。

## <a name="rdteditlock-and-document-modification"></a>RDT_EditLock とドキュメントの変更

前に説明されているフラグは、ドキュメントの非表示の開始を生成することを示します、`RDT_EditLock`ドキュメントが開かれた場合、ユーザーに表示されている**ドキュメント ウィンドウ**します。 この問題が発生すると、ユーザーがで表示されます。 を**保存**求めるときに、表示可能な**ドキュメント ウィンドウ**が閉じられました。 `Microsoft.VisualStudio.Package.Automation.OAProject.CodeModel` 使用する実装、<xref:Microsoft.VisualStudio.Shell.Interop.IVsInvisibleEditorManager>のみに最初に、サービスが動作を`RDT_ReadLock`は (つまり、ドキュメントを開いたときにない視覚的情報を解析する) を取得します。 後で、ドキュメントを変更する必要があります、ロックにアップグレード、弱**RDT_EditLock**します。 ユーザーが表示されているでし、ドキュメントを開く場合**ドキュメント ウィンドウ**、`CodeModel`の弱い`RDT_EditLock`解放されます。

ユーザーが終了した場合、**ドキュメント ウィンドウ**選択**いいえ**、開いているドキュメントを保存するように求められたら、`CodeModel`実装は、ドキュメント内のすべての情報を破棄し、再度開かれます、ディスクの詳細については、ドキュメントに必要な次の時間目に見えない形からドキュメントです。 この動作の細部は、ユーザーが開いたインスタンス、**ドキュメント ウィンドウ**、非表示の開いているドキュメントの変更が閉じるし、選択**いいえ**文書を保存するように求められたらします。 この場合は、ドキュメントがある場合、`RDT_ReadLock`ドキュメントは実際に閉じられましていないおよび文書を保存していないユーザーが選択した場合でもに、変更したドキュメントがメモリを目に見えない形で開いたままです。

ドキュメントの非表示の開始、弱を使用している場合`RDT_EditLock`、ユーザーが文書がはっきりと他のロックが保持されていないときにそのロックを得られます。 ユーザーが閉じたとき、**ドキュメント ウィンドウ**選択**いいえ**ドキュメントの保存を求められたら、ドキュメント閉じる必要がありますメモリから。 つまり、非表示のクライアントは、この状況の発生を追跡するために RDT イベントをリッスンする必要があります。 ドキュメントが必要になる、次に、ドキュメントを再開する必要があります。