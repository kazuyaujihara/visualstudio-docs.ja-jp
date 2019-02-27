---
title: 'エラー: 認証を要求する RPC |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.rpc_requires_authentication
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0bf72110e82fc3cd920f571a5630faafbf2aa5ec
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56696533"
---
# <a name="error-rpc-requires-authentication"></a>エラー : 認証を要求する RPC
Visual Studio デバッガーは、リモート コンピューターに接続できません。 リモート コンピューター上で、リモート デバッグを制限する RPC ポリシーが有効になっています。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1.  実行`\` *windir*`\system32\regedt32.exe`

2.  見つけて削除`HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows NT\RPC\RestrictRemoteClients`します。

3.  コンピューターを再起動してレジストリの変更を有効にします。

4.  問題が解決しない場合について、ドメイン管理者に問い合わせて、**コンピューターの構成 > 管理用テンプレート > システム > リモート プロシージャ コール > 認証されていない RPC クライアントの制限**グループ ポリシー設定です。