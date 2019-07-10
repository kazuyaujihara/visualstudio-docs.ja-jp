---
title: 過剰に要求されたライセンスに対応する | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 02/13/2018
ms.topic: conceptual
description: 管理者が過剰に要求されたサブスクリプションを解決する方法を説明します。
searchscope: VS Subscription
ms.openlocfilehash: 06da8c460e9660857b0f03062bde5bd983bd176d
ms.sourcegitcommit: 32144a09ed46e7223ef7dcab647a9f73afa2dd55
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2019
ms.locfileid: "67586998"
---
# <a name="overallocated-subscriptions"></a>サブスクリプションの割り当て超過

サブスクライバーを追加した後に、注文が変更される場合があります。これにより会社が所有するライセンス数よりも割り当てられたサブスクリプションが多くなる場合があります。 これが発生した場合は、[サブスクライバー] タブにアラートが表示され、詳細情報が提供されます。

> [!NOTE]
> Open License プログラムでは過剰に要求されたサブスクリプション シナリオは許可されません。  また、他のプログラムでは、ポータルにこの情報を別の方式で表示できます。
>
> [!div class="mx-imgBorder"]
> ![過剰に要求されたサブスクリプションの通知](_img/over-claimed/over-claimed-alert.png)

## <a name="resolving-overallocated-subscriptions"></a>サブスクリプションの割り当て超過の解決

ライセンスの割り当て超過を解決するには、次の手順に従います。

1. アラート テキストをクリックします。 これにより、過剰に要求されたサブスクリプション レベルに割り当てられているサブスクライバーと有効期限のフィルター処理された一覧が表示されます。 

2. 必要に応じて、サブスクライバーを削除して、過剰に要求されたライセンスを修正します。 

3. ページの左側にある概要が更新され、再度準拠していることが表示され、過剰要求に関するすべての通知が消えます。 

## <a name="billing-and-true-up"></a>課金とトゥルーアップ

組織に Enterprise Agreement (EA) がある場合、管理者はサブスクリプションを購入せずに割り当てて、後で "トゥルーアップ" と呼ばれる調整プロセスを通して支払うことができます。  割り当て超過が生じると、組織は、"トゥルーアップ" 中にユーザーに割り当てられているサブスクリプションの最大数に対して課金されます。  トゥルーアップの実行時に割り当てられているサブスクリプションが最大数未満になっている場合でも、このことは当てはまります。  最大使用量の監視の詳細については、[最大使用量](maximum-usage.md)に関するトピックを参照してください。

> [!Important]
> Visual Studio Subscriptions with GitHub Enterprise が Visual Studio サブスクリプション管理者によって割り当てられていて、これらのサブスクリプションが一度も購入されていない場合、これらは組織内の GitHub Enterprise 管理者に対して表示されません。 GitHub Enterprise サブスクリプションが表示されるようにするには、最初にサブスクリプションが割り当てられたときに、Visual Studio Professional with GitHub Enterprise または Visual Studio Enterprise with GitHub Enterprise の**少なくとも 1 つの**サブスクリプションを含む購入を行う必要があります。  
>
> 割り当てられている GitHub サブスクリプションごとに、このサブスクリプションのライセンス要件への準拠を維持するために、お客様の責任下で、管理ポータルで対応する Visual Studio with GitHub サブスクリプションが割り当てられていることを確認する必要があります。

[Visual Studio Subscriptions with GitHub Enterprise](assign-github.md) の管理に関する詳細情報をご覧ください。

## <a name="support-resources"></a>サポート リソース

- Visual Studio サブスクリプションの販売、サブスクリプション、アカウント、課金のサポートについては、Visual Studio [サブスクリプション サポート](https://visualstudio.microsoft.com/subscriptions/support/)にお問い合わせください。
