---
title: 同期的に自動的に読み込む拡張機能
ms.date: 02/16/2019
ms.topic: conceptual
ms.assetid: 822e3cf8-f723-4ff1-8467-e0fb42358a1f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8b18642269326c516c2af0baef57cb306f60ae6a
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66316713"
---
# <a name="synchronously-autoloaded-extensions"></a>同期的に自動的に読み込む拡張機能

同期的に自動的に読み込む拡張機能では、Visual Studio のパフォーマンスに悪影響を及ぼすし、非同期 autoload を代わりに変換する必要があります。 Visual Studio 2019 Preview 2 以降は、拡張機能はされているときに同期的に読み込み、ユーザーは通知されます。 拡張機能は読み込むし、通常どおりに動作します。

![拡張機能の互換性に関する警告](media/extension-compatibility-warning.png)

ユーザーは次のとおりです。

- をクリックして**詳細**この情報ページを表示します。

- をクリックして**のパフォーマンスの管理**を開く、[パフォーマンス マネージャー ダイアログ](#performance-manager-dialog)拡張機能とツール windows パフォーマンスの問題を示すです。

- をクリックして**次回からこのメッセージを表示しない**して通知を破棄します。 このオプションを選択すると、同期的に自動的に読み込む拡張機能からの今後のすべての通知も回避されます。 ユーザーは引き続き他の Visual Studio の機能について通知を取得します。

## <a name="performance-manager-dialog"></a>パフォーマンス マネージャー ダイアログ ボックス

![パフォーマンス マネージャー ダイアログ ボックス](media/performance-manager.png)

すべてのユーザー セッションにすべてのパッケージを同期的に読み込まれているすべての拡張機能が、**非推奨の Api**タブ。

* クリックすること、**の詳細については、この問題は**非推奨の Api に関する情報を収集します。
* ユーザーは、移行の進行状況のベンダー拡張機能を連絡することができます。

拡張機能の作成者は、移行する手順を確認できますパッケージで非同期 autoload を[AsyncPackage への移行](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/AsyncPackageMigration)します。

## <a name="specify-synchronous-autoload-settings-using-group-policy"></a>グループ ポリシーを使用して同期 autoload 設定を指定します。

既定では、Visual Studio のインストールのブロックの同期 autoload によって Visual Studio 2019 Update 1 を開始しています。 グループ ポリシーを有効にした場合は、個々 のコンピューターで同期の自動読み込みを許可する Visual Studio を構成できます。 これを行うには、次のキーでレジストリ ベースのポリシーを設定します。

**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\SynchronousAutoload**

エントリ =**許可**

値 = (DWORD)
* **0**は同期 autoload 許可されていません
* **1**同期 autoload は許可されています。

Visual Studio 2019 Update 1 での同期の自動読み込みの設定の詳細については、次を参照してください。、[同期 Autoload 動作](https://aka.ms/AA52xzw)ページ。
