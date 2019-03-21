---
title: RDT_ReadLock の使用法 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RDT_ReadLock
- visible
- RDT_EditLock
- invisible
ms.assetid: b935fc82-9d6b-4a8d-9b70-e9a5c5ad4a55
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 337fa34bce713f743b8962f41a6889335b54b722
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51817452"
---
# <a name="rdtreadlock-usage"></a>RDT_ReadLock の使用法
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> これは、Visual Studio IDE で現在開いているすべてのドキュメントの一覧で、実行されているドキュメント テーブル (RDT)、ドキュメントをロックするためのロジックを提供するフラグ。 このフラグは、ドキュメントが開かれた文書は、ユーザー インターフェイスに表示されるか、メモリの目に見えない形で保持されているかどうかを判断します。  
  
 一般に、使用するよう<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS>次のいずれかが true の場合。  
  
-   ドキュメントを自動的に開く場合、読み取り専用はまだが確立されていることが、<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>所有する必要があります。  
  
-   ユーザーが、ユーザーの前に自動的に開かれたドキュメントを保存するよう求める場合は、UI に表示されることと閉じるましょう。  
  
## <a name="how-to-manage-visible-and-invisible-documents"></a>表示と非表示のドキュメントを管理する方法  
 ユーザーが UI では、ドキュメントを開いたときに、<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>ドキュメントの所有者を確立する必要があります、<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS>フラグを設定する必要があります。 ない場合は<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>所有者が確立されると、その後、ユーザーがクリックしたときに、ドキュメントは保存されません**すべて保存**または IDE を終了します。 かどうか、ドキュメントが開いていない視覚的、メモリ内で変更されていて、ユーザーがシャット ダウン時にドキュメントを保存するように求めまたは保存つまり**すべて保存**を選択した場合、`RDT_ReadLock`は使用できません。 代わりに、使用する必要があります、`RDT_EditLock`を登録し、<xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder>ときに、<xref:Microsoft.VisualStudio.Shell.Interop.__VSREGDOCLOCKHOLDER>フラグ。  
  
## <a name="rdteditlock-and-document-modification"></a>RDT_EditLock とドキュメントの変更  

前述のフラグは、ドキュメントがユーザーによって表示されている **DocumentWindow** に開かれたときに、ドキュメントの不可視のオープンによって `RDT_EditLock` が生成されることを示しています。 この問題が発生すると、表示されている **DocumentWindow** が閉じられたときに **保存** プロンプトが表示されます。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsInvisibleEditorManager> サービスを使用する `Microsoft.VisualStudio.Package.Automation.OAProject.CodeModel` 実装は、最初は `RDT_ReadLock` のみが取得されたとき（つまり、情報を解析するためにドキュメントが表示されないように開かれたとき）に機能します。 後で、ドキュメントを変更する必要がある場合は、ロックは弱い `RDT_EditLock` にアップグレードされます。 ユーザーが表示されている **DocumentWindow** でドキュメントを開くと、`CodeModel` の弱い 弱い `RDT_EditLock` は解放されます。

ユーザーが終了した場合、**ドキュメント ウィンドウ**選択**いいえ**、開いているドキュメントを保存するように求められたら、`CodeModel`実装は、ドキュメント内のすべての情報を破棄し、再度開かれます、ディスクの詳細については、ドキュメントに必要な次の時間目に見えない形からドキュメントです。 この動作の細部は、ユーザーが開いたインスタンス、**ドキュメント ウィンドウ**、非表示の開いているドキュメントの変更が閉じるし、選択**いいえ**文書を保存するように求められたらします。 この場合は、ドキュメントがある場合、`RDT_ReadLock`ドキュメントは実際に閉じられましていないおよび文書を保存していないユーザーが選択した場合でもに、変更したドキュメントがメモリを目に見えない形で開いたままです。  
  
 ドキュメントの非表示の開始、弱を使用している場合`RDT_EditLock`、ユーザーが文書がはっきりと他のロックが保持されていないときにそのロックを得られます。 ユーザーが閉じたとき、**ドキュメント ウィンドウ**選択**いいえ**ドキュメントの保存を求められたら、ドキュメント閉じる必要がありますメモリから。 つまり、非表示のクライアントは、この状況の発生を追跡するために RDT イベントをリッスンする必要があります。 ドキュメントが必要になる、次に、ドキュメントを再開する必要があります。

