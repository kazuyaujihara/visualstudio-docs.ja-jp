---
title: 'エラー: リモートのコンピューターは DCOM 通信を初期化できませんでした。Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.unmarshal_callback_failed
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
ms.openlocfilehash: 9e936292010c73decffadc5b215156f2200ed8b3
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56683075"
---
# <a name="error-remote-computer-could-not-initiate-dcom-communications"></a>エラー : リモート コンピューターは DCOM 通信を初期化できませんでした。
リモート コンピューターがローカル コンピューターと通信しようとしたときに DCOM エラーが発生しました。 ローカル コンピューターは、

 Visual Studio を実行しているコンピューターです。 このエラーが発生する原因は複数あります。

-   ローカル マシンのファイアウォールが有効になっていない。

-   リモート マシンからローカル マシンへの Windows 認証が機能していない。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1.  ローカル コンピューターの Windows ファイアウォールが有効にされている場合は、次を参照してください。[リモート デバッグ](../debugger/remote-debugging.md)ローカル デバッグのファイアウォールを構成する方法についてはします。

2.  リモート サーバーからローカル コンピューターのファイル共有を開いてみて Windows 認証をテストします。

3.  Windows 認証を復元するために、両方のコンピューターを再起動してみます。 Kerberos エラーがないかどうかローカル コンピューターとリモート コンピューターのイベント ログを確認し、既知の問題がないかどうかドメイン管理者に問い合わせてください。

## <a name="see-also"></a>関連項目
 [Remote Debugging](../debugger/remote-debugging.md)