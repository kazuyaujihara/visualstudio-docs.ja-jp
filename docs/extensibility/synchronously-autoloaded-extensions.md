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
ms.openlocfilehash: ad3831fb06d23f622f85a55f5efd0a5650ca5e47
ms.sourcegitcommit: 62149c96de0811415e99bb1e0194e76c320e1a1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "57007164"
---
# <a name="synchronously-autoloaded-extensions"></a>同期的に自動的に読み込む拡張機能

同期的に自動的に読み込む拡張機能では、Visual Studio のパフォーマンスに悪影響を及ぼすし、非同期 autoload を代わりに変換する必要があります。 Visual Studio 2019 Preview 2 以降は、拡張機能はされているときに同期的に読み込み、ユーザーは通知されます。 拡張機能は読み込むし、通常どおりに動作します。

![拡張機能の互換性に関する警告](media/extension-compatibility-warning.png)

ユーザーは次のとおりです。

- をクリックして**詳細**この情報ページを表示します。

- をクリックして**のパフォーマンスの管理**を開く、[パフォーマンス マネージャー ダイアログ](#performance-manager-dialog)拡張機能とツール windows パフォーマンスの問題を示すです。

- をクリックして**次回からこのメッセージを表示しない**して通知を破棄します。 このオプションを選択すると、同期的に自動的に読み込む拡張機能からの今後のすべての通知も回避されます。 ユーザーは引き続き他の Visual Studio の機能について通知を取得します。

### <a name="performance-manager-dialog"></a>パフォーマンス マネージャー ダイアログ ボックス

![パフォーマンス マネージャー ダイアログ ボックス](media/performance-manager.png)

すべてのユーザー セッションにすべてのパッケージを同期的に読み込まれているすべての拡張機能が、**非推奨の Api**タブ。

* クリックすること、**の詳細については、この問題は**非推奨の Api に関する情報を収集します。
* ユーザーは、移行の進行状況のベンダー拡張機能を連絡することができます。

拡張機能の作成者は、移行する手順を確認できますパッケージで非同期 autoload を[AsyncPackage への移行](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/AsyncPackageMigration)します。
