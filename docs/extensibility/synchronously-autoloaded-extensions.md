---
title: 同期的に自動的に読み込む拡張機能
ms.date: 02/16/2019
ms.topic: conceptual
ms.assetid: 822e3cf8-f723-4ff1-8467-e0fb42358a1f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 960fd54564bc25a8338461c30cd8a893e277b5a5
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "56844582"
---
# <a name="synchronously-autoloaded-extensions"></a>同期的に自動的に読み込む拡張機能

同期的に自動的に読み込む拡張機能では、Visual Studio のパフォーマンスに悪影響を及ぼすし、非同期 autoload を代わりに変換する必要があります。 Visual Studio 2019 Preview 2 以降、拡張機能はされているときに同期的に読み込みユーザーに通知します。 拡張機能は読み込むし、通常どおりに動作します。

![拡張機能の互換性に関する警告](media/extension-compatibility-warning.png)

1. クリックする**詳細**この情報ページを表示します。

3. クリックする**のパフォーマンスの管理**を開く、[パフォーマンス マネージャー ダイアログ](#performance-manager-dialog)拡張機能とツール windows パフォーマンスの問題を示すです。

3. クリックする**次回からこのメッセージを表示しない**して通知を破棄します。 このオプションを選択すると、同期的に自動的に読み込む拡張機能からの今後のすべての通知も防止します。 ユーザーは引き続き他の Visual Studio の機能で通知を受け取る。

### <a name="performance-manager-dialog"></a>パフォーマンス マネージャー ダイアログ ボックス

  ![パフォーマンス マネージャー ダイアログ ボックス](media/performance-manager.png)

すべてのユーザー セッションにすべてのパッケージを同期的に読み込まれているすべての拡張機能に表示されます、**非推奨の Api**タブ。

* クリックすること、**の詳細については、この問題は**非推奨の Api に関する情報を収集します。
* ユーザーは、移行の進行状況のベンダー拡張機能を連絡することができます。

拡張機能の作成者は、移行する手順を確認できますパッケージで非同期 autoload を[AsyncPackage への移行](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/AsyncPackageMigration)します。
