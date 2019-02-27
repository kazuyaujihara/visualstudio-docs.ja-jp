---
title: サブスクリプション情報のエクスポート | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 03/14/2018
ms.topic: conceptual
description: サブスクライバーの一覧とサブスクリプションの割り当ての詳細をエクスポートする方法について説明します。
searchscope: VS Subscription
ms.openlocfilehash: 7e2db1c0de036441801aa56ae1956d0a10719798
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "56844030"
---
# <a name="exporting-subscription-information"></a>サブスクリプション情報のエクスポート

Visual Studio サブスクリプションの[管理ポータル](https://manage.visualstudio.com)では、ユーザーの一覧とその割り当てに関する詳細情報をエクスポートできます。 この情報には、名前、メール アドレス、連絡用メール アドレス、サブスクリプション レベル、割り当て日、ライセンス認証の状態、有効期限、参照フィールド、有効なダウンロード、国、言語、サブスクリプションの状態、サブスクリプション GUID が含まれます。

この機能は、割り当てや有効期限の追跡をはじめ、いくつかのシナリオで役立ちます。 たとえば、BAN から GUID の使用に切り替えてサブスクリプションの割り当てを追跡する場合、このレポートと Microsoft Excel の VLOOKUP 式を使用して、サブスクライバーを適切に照合することができます。

**[エクスポート]** タブを選択するだけでエクスポートが実行され、ファイルはローカル コンピューターにダウンロードされます。 このファイルには、ユーザー サブスクリプションを含む割り当ての名前と、エクスポートの日付が含まれます。
> [!div class="mx-imgBorder"]
> ![サブスクライバーのエクスポート](_img/exporting-subscriptions/exporting-subscriptions.png)
