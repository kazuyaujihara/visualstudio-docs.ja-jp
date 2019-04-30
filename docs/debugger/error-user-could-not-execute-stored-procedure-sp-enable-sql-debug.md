---
title: エラー :ユーザーがいない実行ストアド プロシージャ sp_enable_sql_debug |Microsoft Docs
ms.date: 11/04/2016
ms.topic: troubleshooting
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
ms.openlocfilehash: e051cd594ee26a57fdbb7dcdc5bdad81f06cf771
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850085"
---
# <a name="error-user-could-not-execute-stored-procedure-spenablesqldebug"></a>エラー :ユーザーがストアド プロシージャ sp_enable_sql_debug を実行できませんでした

ストアド プロシージャ sp_enable_sql_debug がサーバーで実行できません。 考えられる原因を以下に示します。

- 接続の問題。 サーバーへの接続が安定している必要があります。

- サーバーで必要な権限の不足。 SQL Server 2005 でデバッグするには、Visual Studio を実行するアカウントと SQL Server に接続するために使用するアカウントの両方が sysadmin ロールのメンバーであることが必要です。 SQL Server に接続するために使用するアカウントは、使用している Windows ユーザー アカウント (Windows 認証を使用している場合) またはユーザー ID とパスワードが設定されたアカウント (SQL 認証を使用している場合) です。

詳細については、「[方法 :デバッグ用の SQL Server のアクセス許可の設定](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414)します。

## <a name="see-also"></a>関連項目

- [方法: デバッグ用の SQL Server のアクセス許可を設定します。](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414)
- [SQL デバッグの設定](/previous-versions/visualstudio/visual-studio-2010/s4sszxst\(v\=vs.100\))