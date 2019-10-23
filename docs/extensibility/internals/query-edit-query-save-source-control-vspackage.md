---
title: クエリの編集クエリの保存 (ソース管理 VSPackage) |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- QEQS events
- Query Edit Query Save events
- source control packages, Query Edit Query Save events
ms.assetid: c360d2ad-fe42-4d65-899d-d1588cc8a322
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: be12297bdaeb112d7421b02da1153ed62d6d14f8
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72724770"
---
# <a name="query-edit-query-save-source-control-vspackage"></a>クエリの編集とクエリの保存 (ソース管理 VSPackage)
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] エディターでは、クエリの編集クエリの保存 (QEQS) イベントをブロードキャストできます。 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ソース管理スタブは、qeqs イベントの受信者になるように、QEQS サービスを実装します。 これらのイベントは、現在アクティブなソース管理 VSPackage に委任されます。 アクティブなソース管理 VSPackage は、<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> とそのメソッドを実装します。 @No__t_0 インターフェイスのメソッドは、通常、ドキュメントが最初に編集される直前と、ドキュメントが保存される直前に呼び出されます。

## <a name="queryeditquerysave-events"></a>QueryEditQuerySave イベント
 ソース管理 VSPackage は、`IVsQueryEditQuerySave2` インターフェイスと必要なメソッドを実装することによって、QEQS イベントを処理する必要があります。 少なくとも VSPackage が実装する必要がある2つのメソッドについて、以下に簡単に説明します。 実際の実装は、ソース管理モデルのロジックに従っている必要があります。

### <a name="queryeditfiles-method"></a>QueryEditFiles メソッド
 @No__t_0 は、プロジェクトまたはエディターでファイルを変更する場合に呼び出されます。 このメソッドは、ファイルが変更される前とファイルが保存される*前に*呼び出されるのが理想的です。 @No__t_0 メソッドは、呼び出されると、指定されたファイルがソース管理下にあるかどうか、チェックアウトする必要があるかどうか、およびそれらを再読み込みできるかどうかをチェックします。 状況によってファイルを編集できないようにする場合、`IVsQueryEditQuerySave2::QueryEditFiles` メソッドは、呼び出し元のプログラムに対して編集をキャンセルするように指示します。 呼び出し元が呼び出しモードを指定することもできます。 "サイレント" モードでは、このメソッドは UI が表示されない場合にのみアクションを実行します。 UI が避けられない場合は、問題を示すフラグを返す必要があります。

 メソッドはトランザクション方式で動作します。つまり、1つのファイルで編集がキャンセルされた場合、すべてのファイルに対して編集がキャンセルされます。 逆に、編集が許可されている場合は、すべてのファイルに対して許可されます。 このメソッドによって、特定のファイルセットに対して1回の編集が許可される場合は、同じファイルセットに対する後続の呼び出しでの編集が常に許可されている必要があります。 Allow-edit ループは、ファイルが閉じられ、保存されて、再読み込みされるまで続行されます。属性 (プロパティ) が変更されるまで、または、ソース管理パッケージが変更されます。 @No__t_0 メソッドを実装する際に考慮すべきケースとしては、複数のファイル、特別なファイル、ユーザーからのキャンセル、メモリ内の編集などがあります。

### <a name="querysavefiles-method"></a>QuerySaveFiles メソッド
 @No__t_0 は、プロジェクトまたはエディターがファイルのセットを保存する必要がある場合に呼び出されます。 @No__t_0 メソッドは、呼び出されると、指定されたファイルが読み取り専用かどうか、およびソース管理下にあるかどうかを確認します。 ファイルをチェックアウトする必要がある場合は、呼び出しがソース管理パッケージに委任されます。 状況によってファイルが保存されないようにするには、`IVsQueryEditQuerySave2::QuerySaveFiles` メソッドで、保存をキャンセルするようにエディターに指示する必要があります。 @No__t_0 メソッドと同様に、呼び出し元が呼び出しモードを指定することもできます。 "サイレント" モードでは、このメソッドは UI が表示されない場合にのみアクションを実行します。 UI が避けられない場合は、問題を示すフラグを返す必要があります。

 このメソッドは、トランザクション方式で動作する必要があります。つまり、1つのファイルで保存がキャンセルされた場合、すべてのファイルに対して保存が取り消されます。 逆に、保存が許可されている場合は、すべてのファイルに対して保存が許可されている必要があります。 @No__t_0 方法と同様に、`IVsQueryEditQuerySave2::QuerySaveFiles` メソッドの実装で考慮すべきケースとして、複数のファイル、特別なファイル、ユーザーからのキャンセル、メモリ内の編集があります。

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>