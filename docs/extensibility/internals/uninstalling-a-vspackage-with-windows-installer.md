---
title: Windows インストーラー | を使用した VSPackage のアンインストールMicrosoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- packages, uninstalling
- VSPackages, uninstalling
- uninstalling VSPackages
ms.assetid: c4575ac7-82da-4af8-a375-ea756a101fbf
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a8e92937e848d124c18dc91b9bdfa0f020f27f20
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72722125"
---
# <a name="uninstalling-a-vspackage-with-windows-installer"></a>Windows インストーラーによる VSPackage のアンインストール
ほとんどの場合 Windows インストーラー、VSPackage をアンインストールするには、VSPackage をインストールしたことを "元に戻す" だけで済みます。 「[インストール後に実行する必要](../../extensibility/internals/commands-that-must-be-run-after-installation.md)のあるコマンド」で説明されているカスタムアクションもアンインストール後に実行する必要があります。 インストールとアンインストールの両方について、InstallFinalize 標準アクションの直前に devenv.exe の呼び出しが行われるため、CustomAction および InstallExecuteSequence テーブルエントリは両方のケースに対応します。

> [!NOTE]
> MSI パッケージをアンインストールした後、`devenv /setup` を実行します。

 一般的なルールとして、Windows インストーラーパッケージにカスタムアクションを追加する場合は、アンインストール時およびロールバック時にそれらのアクションを処理する必要があります。 たとえば、VSPackage を自己登録するカスタムアクションを追加する場合は、カスタムアクションを追加して、登録を解除する必要があります。

> [!NOTE]
> ユーザーは、VSPackage をインストールしてから、統合されている [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] のバージョンをアンインストールすることができます。 @No__t_0 の依存関係があるコードを実行するカスタムアクションを排除することで、そのシナリオで VSPackage のアンインストールが確実に機能するようにすることができます。

## <a name="handling-launch-conditions-at-uninstall-time"></a>アンインストール時に起動条件を処理する
 Launchconditions 標準アクションは、条件が満たされていない場合にエラーメッセージを表示するために、Launchconditions テーブルの行を読み取ります。 システム要件が満たされていることを確認するために一般的に使用される起動条件として、`NOT Installed` の条件を Launchconditions テーブルの LaunchConditions 行に追加することにより、アンインストール中に起動条件をスキップできます。

 別の方法として、アンインストール時に重要でない起動条件を `OR Installed` を追加することもできます。 これにより、アンインストール中に条件が常に true になるため、起動条件エラーメッセージは表示されません。

> [!NOTE]
> `Installed` は、VSPackage が既にシステムにインストールされていることを検出したときに設定 Windows インストーラープロパティです。

## <a name="see-also"></a>関連項目
- [Windows インストーラー](https://msdn.microsoft.com/library/187d8965-c79d-4ecb-8689-10930fa8b3b5)
- [システム要件の検出](../../extensibility/internals/detecting-system-requirements.md)