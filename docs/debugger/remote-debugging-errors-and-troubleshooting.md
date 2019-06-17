---
title: リモート デバッグ エラーとトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: 078551111223f11b38f3192075caa9ddfabaf18c
ms.sourcegitcommit: 9753c7544cec852ca5efd0834e0956d9e53a5734
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2019
ms.locfileid: "67043349"
---
# <a name="remote-debugging-errors-and-troubleshooting"></a>リモート デバッグ エラーとトラブルシューティング

リモートでデバッグする際は、次のエラーを遭遇する可能性があります。

- [エラー: サーバーに自動的にステップ インできません](../debugger/error-unable-to-automatically-step-into-the-server.md)

- [エラー: Microsoft Visual Studio リモート デバッグ モニター (MSVSMON.EXE) は、リモート コンピューター上では実行されていません。](/visualstudio/debugger/error-remote-debugging-monitor-msvsmon-exe-does-not-appear-to-be-running)

- [Unable to Connect to the Microsoft Visual Studio Remote Debugging Monitor](../debugger/unable-to-connect-to-the-microsoft-visual-studio-remote-debugging-monitor.md)

- [エラー: リモート コンピューターが [リモート接続] ダイアログに表示されません](../debugger/error-remote-machine-does-not-appear-in-a-remote-connections-dialog.md)

## <a name="run-the-remote-debugger-as-an-administrator"></a>リモート デバッガーを管理者として実行します。

管理者としてリモート デバッガーを実行しなかった場合、問題遭遇する可能性があります。 たとえば、次のエラーを参照してください可能性があります。"Visual Studio リモート デバッガー (MSVSMON します。EXE) がこのプロセスをデバッグする権限がありません。" アプリケーション (サービスではなく) としてリモート デバッガーを実行する場合、[別のユーザー アカウント](error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user.md)エラー。

### <a name="when-running-the-remote-debugger-as-a-service"></a>リモート デバッガーをサービスとして実行する場合

S サービスとしてリモート デバッガーを実行するときに、いくつかの理由を管理者として実行することお勧めします。

- リモート デバッガー サービスは、接続のみを許可、管理者から、**ありません**管理者として実行することによって導入された新しいセキュリティ上のリスクです。

- Visual Studio のユーザーがリモート デバッガー自体よりもプロセスをデバッグする複数の権限を持つ場合の結果はエラーできなくなることができます。

- セットアップし、リモート デバッガーの構成を簡略化します。

管理者としてリモート デバッガーを実行せずにデバッグすることはできますが、この作業を正しく行うをいくつかの要件があるし、多くの場合より高度なサービスの構成手順が必要があります。

- リモート コンピューターでを使用しているアカウントが必要、**サービスとしてログオン**特権。 追加するログオン サービスとして"セクションの手順を参照してください、[接続できません。](error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md)エラーに関する記事。

- アカウントは、ターゲット プロセスをデバッグする権限が必要です。 これらの権利を取得するには、デバッグするプロセスとして、同じアカウントでリモート デバッガーを実行する必要があります。 (代わりに簡単には、サービス管理者として実行するのには) です。 

- アカウントは (つまりでの認証) に接続できる必要があります、ネットワーク経由で Visual Studio コンピューター。 ドメインでは、組み込みのローカル システムや Network Service アカウントまたはドメイン アカウントでリモート デバッガーが実行されている場合の接続を簡単になります。 ビルトイン アカウントには、セキュリティ上のリスクを提示できるセキュリティ権限が昇格されました。

### <a name="when-running-the-remote-debugger-as-an-application-normal-mode"></a>アプリケーション (通常モード) としてリモート デバッガーを実行する場合

管理者特権以外 (通常のアプリケーション) などのプロセスにアタッチしようとすると、管理者としてリモート デバッガーを実行している場合は関係ありません。

いくつかのシナリオで、管理者としてリモート デバッガーを実行するには。

- 別のユーザーとして実行されているプロセスにアタッチする (場合など IIS のデバッグ)、または

- 別のプロセスを起動しようとしてとを起動するプロセスは管理者です。

操作を行う**いない**場合は、プロセスを起動して、プロセスを起動する必要がありますを管理者として実行する**いない**管理者であります。

## <a name="see-also"></a>関連項目
- [Remote Debugging](../debugger/remote-debugging.md)