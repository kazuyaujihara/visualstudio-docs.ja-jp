---
title: 'エラー: マシンに接続できません&lt;名前&gt;します。 ネットワーク上にコンピューターが見つかりません。 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.remote.dcom_disabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- DCOM, unable to connect error
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f6dc7a9b5e066304e27e784312707400d9571a60
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686575"
---
# <a name="error-unable-to-connect-to-the-machine-ltnamegt-the-machine-cannot-be-found-on-the-network"></a>エラー: マシンに接続できません&lt;名前&gt;します。 ネットワーク上にコンピューターが見つかりません。
このエラーは、次の条件のいずれかが満たされると発生します。

-   リモート コンピューターへの接続が解除された。

-   リモート コンピューターのユーザー アカウントが無効になっている。

-   リモート コンピューターのパスワードの有効期限が切れている。

### <a name="to-resolve-this-behavior"></a>この問題を解決するには

-   ローカル コンピューターとリモート コンピューターが同じネットワーク上に存在することを確認します。 これを行うには、Microsoft Windows エクスプローラー (ファイル エクスプローラー) を使用してリモート コンピューターにアクセスしてみます。

     および

-   リモート コンピューターへの接続に使用しているユーザー アカウントが有効になっていることを確認します。

     および

-   リモート コンピューターへの接続に使用しているパスワードが有効であり、有効期限が切れていないことを確認します。

## <a name="see-also"></a>参照
- [Remote Debugging](../debugger/remote-debugging.md)
- [デバッガーの設定と準備](../debugger/debugger-settings-and-preparation.md)