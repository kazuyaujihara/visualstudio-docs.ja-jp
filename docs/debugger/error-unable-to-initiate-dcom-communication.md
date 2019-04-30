---
title: エラー :DCOM 通信を開始できません |。Microsoft Docs
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.unmarshal_server_failed
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
ms.openlocfilehash: 1112ec72e8aca764f749a6d8f1925302f569b17e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850071"
---
# <a name="error-unable-to-initiate-dcom-communication"></a>エラー :DCOM 通信を初期化できません。
ローカル コンピューターがリモート コンピューターと通信しようとしたときに DCOM エラーが発生しました。 このエラーは、リモート サーバーのファイアウォール、またはリモート コンピューターで Windows 認証が破損していることに原因があります。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- リモート コンピューターの Windows ファイアウォールが有効にされている場合は、次を参照してください。[リモート デバッグ](../debugger/remote-debugging.md)ローカル デバッグのファイアウォールを構成する方法についてはします。

- Windows 認証を復元するために、両方のコンピューターを再起動してみます。 Kerberos エラーがないかどうかローカル コンピューターとリモート コンピューターのイベント ログを確認し、既知の問題がないかどうかドメイン管理者に問い合わせてください。

## <a name="see-also"></a>関連項目
- [Remote Debugging](../debugger/remote-debugging.md)