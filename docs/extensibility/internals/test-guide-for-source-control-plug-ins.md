---
title: ソース管理プラグインのテストガイド |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- plug-ins, source control
- source control [Visual Studio SDK], testing plug-ins
- tests, source control plug-ins
- testing, source control plug-ins
- source control plug-ins, test guide
ms.assetid: 13b74765-0b7c-418e-8cd9-5f2e8db51ae5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 51595708bf30472fd001bde394c7d8c80e39ad45
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72722404"
---
# <a name="test-guide-for-source-control-plug-ins"></a>ソース管理プラグイン向けのテスト ガイド
このセクションでは、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] を使用したソース管理プラグインのテストに関するガイダンスを提供します。 最も一般的なテスト領域の概要と、問題がある可能性がある複雑な領域の一部を紹介します。 この概要は、テストケースの完全な一覧ではありません。

> [!NOTE]
> 最新の [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE のバグ修正と機能強化によって、以前のバージョンの [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] を使用していなかった既存のソース管理プラグインに関する問題が明らかになることがあります。 以前のバージョンの [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 以降、プラグインに変更が加えられていない場合でも、このセクションで列挙されている領域については、既存のソース管理プラグインをテストすることを強くお勧めします。

## <a name="common-preparation"></a>一般的な準備
 @No__t_0 とターゲットソース管理プラグインがインストールされているコンピューターが必要です。 同様に構成された2つ目のコンピューターは、オープンソース管理テストの一部で使用できます。

## <a name="definition-of-terms"></a>用語の定義
 このテストガイドでは、次の用語定義を使用します。

 クライアントプロジェクトソース管理の統合をサポートする [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] で使用できるプロジェクトの種類 ([!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]、[!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]、[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] など)。

 Web プロジェクトには、ファイルシステム、ローカル IIS、リモートサイト、FTP の4種類の Web プロジェクトがあります。

- ファイルシステムプロジェクトはローカルパスに作成されますが、UNC パスを使用して内部でアクセスされるため、インターネットインフォメーションサービス (IIS) をインストールする必要はありません。また、クライアントプロジェクトと同様に、IDE 内からソース管理下に配置することもできます。

- ローカル IIS プロジェクトは、同じコンピューターにインストールされ、ローカルコンピューターを指す URL を使用してアクセスされる IIS で動作します。

- リモートサイトプロジェクトは IIS サービスの下にも作成されますが、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE 内からではなく、IIS サーバーコンピューターのソース管理下に配置されます。

- FTP プロジェクトはリモート FTP サーバーを介してアクセスされますが、ソース管理下に配置することはできません。

  ソース管理下にあるソリューションまたはプロジェクトに対するもう1つの用語。

  バージョンストアソース管理プラグイン API を使用してアクセスされているソース管理データベース。

## <a name="test-areas-covered-in-this-section"></a>このセクションで説明されているテスト領域

- [テスト領域 1: ソース管理への追加とオープン](../../extensibility/internals/test-area-1-add-to-open-from-source-control.md)

  - ケース 1a: ソース管理にソリューションを追加する

  - ケース 1b: ソース管理からソリューションを開く

  - ケース 1c: ソース管理からソリューションを追加する

- [テスト領域 2: ソース管理からの取得](../../extensibility/internals/test-area-2-get-from-source-control.md)

- [テスト領域 3: チェックアウトとチェックアウトの取り消し](../../extensibility/internals/test-area-3-check-out-undo-checkout.md)

  - ケース 3: チェックアウト/チェックアウトの取り消し

  - ケース 3a: チェックアウト

  - ケース 3b: 切断されたチェックアウト

  - ケース 3c: クエリの編集/クエリの保存 (QEQS)

  - ケース 3d: サイレントチェックアウト

  - ケース 3e: チェックアウトを元に戻す

- [テスト領域 4: チェックイン](../../extensibility/internals/test-area-4-check-in.md)

  - ケース 4a: 変更された項目

  - ケース 4b: ファイルの追加

  - ケース 4c: プロジェクトの追加

- [テスト領域 5: ソース管理の変更](../../extensibility/internals/test-area-5-change-source-control.md)

  - ケース 5a: バインド

  - ケース 5b: バインド解除

  - ケース 5c: 再バインド

- [テスト領域 6: 削除](../../extensibility/internals/test-area-6-delete.md)

- [テスト領域 7: 共有](../../extensibility/internals/test-area-7-share.md)

- [テスト領域 8: プラグインの切り替え](../../extensibility/internals/test-area-8-plug-in-switching.md)

  - ケース 8a: 自動変更

  - Case 8b: ソリューションベースの変更

## <a name="see-also"></a>関連項目
- [ソース管理プラグイン](../../extensibility/source-control-plug-ins.md)
