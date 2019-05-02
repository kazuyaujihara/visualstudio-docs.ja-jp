---
title: エラー :リモート コンピューターは DCOM 通信を開始できませんでした。Microsoft Docs
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
ms.openlocfilehash: 7ceb796b3a4b3cbc2b239a09ac8c173e746f194c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850897"
---
# <a name="error-remote-computer-could-not-initiate-dcom-communications"></a>エラー :リモート コンピューターは DCOM 通信を初期化できませんでした
リモート コンピューターがローカル コンピューターと通信しようとしたときに DCOM エラーが発生しました。 ローカル コンピューターは、

 Visual Studio を実行しているコンピューターです。 このエラーが発生する原因は複数あります。

- ローカル マシンのファイアウォールが有効になっていない。

- リモート マシンからローカル マシンへの Windows 認証が機能していない。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. ローカル コンピューターの Windows ファイアウォールが有効にされている場合は、次を参照してください。[リモート デバッグ](../debugger/remote-debugging.md)ローカル デバッグのファイアウォールを構成する方法についてはします。

2. リモート サーバーからローカル コンピューターのファイル共有を開いてみて Windows 認証をテストします。

3. Windows 認証を復元するために、両方のコンピューターを再起動してみます。 Kerberos エラーがないかどうかローカル コンピューターとリモート コンピューターのイベント ログを確認し、既知の問題がないかどうかドメイン管理者に問い合わせてください。

## <a name="see-also"></a>関連項目
 [Remote Debugging](../debugger/remote-debugging.md)