---
title: RPC デバッグを使用して COM クライアントおよびサーバーをデバッグする |Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.com
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- RPC (Remote Procedure Call), debugging COM clients and servers
- COM, debugging
- RPC (Remote Procedure Call)
- RPC (Remote Procedure Call), debugging
- COM clients, debugging
- COM servers, debugging
- out-of-process remote procedure call debugging
- remote debugging, RPC (Remote Procedure Call)
- in-process remote procedure call debugging
ms.assetid: 3e8526c8-43b5-4b87-8e0d-b22c24f0a3ea
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 83fdfa65f4efb6f0bc0b99eac27ae0e57c79e3cd
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72733688"
---
# <a name="how-to-debug-com-clients-and-servers-using-rpc-debugging"></a>方法 : RPC デバッグを使用して COM クライアントおよびサーバーをデバッグする
リモート プロシージャ コール (RPC: Remote Procedure Call) デバッグを使用して、COM クライアント/サーバー アプリケーションをデバッグできます。 このデバッグを行うには、あらかじめ RPC デバッグを有効にする必要があります。 RPC デバッグを有効にすると、ステップ実行でクライアントからサーバーを呼び出すときに、デバッガーがサーバーにアタッチし、コードのデバッグができるようになります。 デバッガーをアタッチすることにより、クライアントおよびサーバーのどちらのプロセスでも、デバッガーのすべての機能を使用できます。

### <a name="to-enable-rpc-debugging"></a>RPC デバッグを有効にするには

1. **[ツール]** メニューの **[オプション]** をクリックします。

2. **[オプション]** ダイアログ ボックスで、 **[デバッグ]** フォルダーをクリックします。

3. **[ネイティブ]** ページをクリックします。

4. **[RPC デバッグ]** チェック ボックスをオンにします。

    > [!NOTE]
    > RPC 呼び出しをデバッグするには、管理者またはパワー ユーザーの権限が必要です。

    > [!NOTE]
    > Microsoft Windows Vista が実行されているリモート サーバーへの RPC ステップ実行は、そのリモート サーバーにネイティブ デバッガーがアタッチされている場合のみ機能します。 それ以外の場合、エラー メッセージが表示されることなく RPC 呼び出しが失敗します。 何らかの方法で RPC 呼び出しに成功したとしても、RPC 呼び出しへのステップ インは正常に機能しません。

## <a name="see-also"></a>関連項目
- [COM サーバーおよび COM コンテナーのデバッグ](../debugger/com-server-and-container-debugging.md)
- [Visual Studio でのデバッグ](../debugger/index.yml)
- [デバッガーでのはじめに](../debugger/debugger-feature-tour.md)