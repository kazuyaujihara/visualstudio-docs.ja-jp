---
title: リモートデバッグエラーとトラブルシューティング |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, errors
- debugging errors
- remote debugging, troubleshooting
- troubleshooting remote debugging
- errors [debugger], remote debugging
- remote debugging, errors
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8b413ce193e6761d515de5bc5ef30fae8e18a3a3
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73187517"
---
# <a name="remote-debugging-errors-and-troubleshooting"></a>リモート デバッグ エラーとトラブルシューティング

リモートでデバッグを試行すると、次のエラーが発生する場合があります。

- [Error: Unable to Automatically Step Into the Server](../debugger/error-unable-to-automatically-step-into-the-server.md)

- [エラー : Microsoft Visual Studio リモート デバッグ モニター (MSVSMON.EXE) は、リモート コンピューター上では実行されていません。](error-remote-debugging-monitor-msvsmon-exe-does-not-appear-to-be-running.md)

- [Unable to Connect to the Microsoft Visual Studio Remote Debugging Monitor](../debugger/unable-to-connect-to-the-microsoft-visual-studio-remote-debugging-monitor.md)

- [エラー: リモート コンピューターが [リモート接続] ダイアログに表示されません](../debugger/error-remote-machine-does-not-appear-in-a-remote-connections-dialog.md)

## <a name="run-the-remote-debugger-as-an-administrator"></a>管理者としてリモートデバッガーを実行する

リモートデバッガーを管理者として実行しないと、問題が発生する可能性があります。 たとえば、次のエラーが表示されることがあります。 "Visual Studio リモートデバッガー (MSVSMONEXE) には、このプロセスをデバッグするための十分な特権がありません。 " (サービスではなく) アプリケーションとしてリモートデバッガーを実行している場合は、[異なるユーザーアカウント](error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user.md)エラーが表示されることがあります。

### <a name="when-running-the-remote-debugger-as-a-service"></a>リモートデバッガーをサービスとして実行する場合

リモートデバッガーを s サービスとして実行する場合は、いくつかの理由から管理者として実行することをお勧めします。

- リモートデバッガーサービスでは管理者からの接続のみが許可されるため、管理者として実行しても新しいセキュリティリスクは発生し**ません**。

- これにより、Visual Studio ユーザーにプロセスをデバッグする権限がリモートデバッガー自体よりも多くある場合に発生するエラーを防ぐことができます。

- リモートデバッガーのセットアップと構成を簡略化します。

リモートデバッガーを管理者として実行せずにデバッグすることもできますが、これを正しく動作させるための要件がいくつかあり、多くの場合、より高度なサービス構成手順が必要になります。

- リモートコンピューターで使用しているアカウントには、"**サービスとしてログオン**" 権限が必要です。 「サービスとしてのログオンを追加する[には」](error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md)の手順を参照してください。

- このアカウントは、ターゲットプロセスをデバッグする権限を持っている必要があります。 これらの権限を取得するには、デバッグするプロセスと同じアカウントでリモートデバッガーを実行する必要があります。 (簡単な方法は、管理者としてサービスを実行することです)。 

- アカウントは、ネットワーク経由で Visual Studio コンピューターに接続して (つまり、認証する) 必要があります。 ドメインでは、リモートデバッガーが組み込みのローカルシステムアカウントまたはネットワークサービスアカウントまたはドメインアカウントで実行されている場合、接続が簡単になります。 ビルトインアカウントには、セキュリティ上のリスクをもたらす可能性がある、管理者特権のセキュリティ特権があります。

### <a name="when-running-the-remote-debugger-as-an-application-normal-mode"></a>リモートデバッガーをアプリケーションとして実行する場合 (通常モード)

(通常のアプリケーションなどの) 独自の昇格されていないプロセスにアタッチしようとする場合は、リモートデバッガーを管理者として実行しているかどうかは関係ありません。

次のようないくつかのシナリオで、管理者としてリモートデバッガーを実行します。

- 別のユーザー (IIS のデバッグ時など) として実行されているプロセスにアタッチする場合は、

- 別のプロセスを起動しようとしています。起動するプロセスは管理者です。

プロセスを起動する必要があり、起動するプロセスが管理者で**ない**場合は、を管理者として実行**しないよう**にします。

## <a name="see-also"></a>関連項目
- [Remote Debugging](../debugger/remote-debugging.md)