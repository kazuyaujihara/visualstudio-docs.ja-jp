---
title: VLSC に表示される個人メール
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/24/2019
ms.topic: conceptual
description: 'Visual Studio のサブスクリプション: サブスクライバーに Hotmail や Gmail のアドレスが表示される理由'
ms.openlocfilehash: 8418a177e793f0b4fe9a5019d2cf62fa724312ff
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2019
ms.locfileid: "68605757"
---
# <a name="visual-studio-subscriptions--why-am-i-seeing-hotmail-or-gmail-addresses-for-my-subscribers"></a>Visual Studio のサブスクリプション: サブスクライバーに Hotmail や Gmail のアドレスが表示される理由
ボリューム ライセンス サービス センター (VLSC) から Visual Studio の新しい[サブスクリプション管理ポータル](https://manage.visualstudio.com)に移行した後、一部のサブスクライバーの "サインイン用のメール アドレス" として、Hotmail、Gmail や Yahoo などのサードパーティのメール アドレスが表示され、管理者が驚くことがありました。  詳細については、[こちらの動画](https://www.youtube.com/watch?v=J61EYaVN-dQ&list=PLReL099Y5nReJhZ6o8CQFPSBgzGCHX99_&index=6)を確認してください。

## <a name="cause"></a>原因
このシナリオは、従来の MSDN サブスクライバー エクスペリエンスにサインイン プロセスが関連付けられていることによって発生します。 ユーザーはボリューム ライセンス サービス センター (VLSC) から Visual Studio のサブスクリプション管理ポータルに、変更なく移行されました。 管理者は、ユーザーが個人アカウントを使用して、サブスクリプションの特典にアクセスしていたことを知らなかった可能性があります。 2016 年で完了した Visual Studio のサブスクライバーの移行以前は、Visual Studio のサブスクリプションを使用には、2 回アクションを実行する必要がありました。
1. 管理者が、個々のサブスクライバーに、職場または学校のメール アドレスを使用してサブスクリプションを “割り当て” ます。
2. そのサブスクリプションをサブスクライバーが “アクティブ化” します。

サブスクライバーのアクティブ化処理中には、次が発生します。サインインに Microsoft アカウント (MSA) が求められます。 サブスクライバーが職場または学校のアカウント (例: tasha@contoso.com) を MSA にしない場合、新しい MSA を作成するか、既存のものが利用されます。 これにより、“サインイン電子メール アドレス” が “割り当てられたメール アドレス” と異なってしまいます。

> [!NOTE]
> [https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs) の新しいサブスクライバー エクスペリエンスでは、職場/学校と Microsoft アカウント (MAA) の両種類の ID をサポートしています。

最後に、管理者による移行では、新しいサブスクライバーの管理に使用するサブスクライバーの "サインイン電子メール アドレス" が VLSC のデータから取得されたため、最近移行を行った管理者にとっては、ユーザー インターフェイスの変更によって、以前は気付かなかった個人アカウントがより目立つようになりました。

## <a name="solution"></a>ソリューション
この問題を解決するには、サブスクライバーの情報を編集して、サインイン用のメール アドレスを更新する必要があります。  編集はサブスクライバーごとに個々に行うことも、一括で行うことも可能です。 完全な詳細については、[サブスクリプションの編集](edit-license.md)に関する記事を参照してください。

##  <a name="next-steps"></a>次の手順
- サブスクライバーのメール アドレスを更新したら、サインイン情報が変更されたことをサブスクライバーに通知することもできます。  更新された情報が含まれる電子メールも送信されます。
- 組織内の[サブスクライバーの一覧をフィルター処理](search-license.md)して、変更が必要な可能性のあるサインイン用メールアドレスを検索すると便利な場合があります。  

