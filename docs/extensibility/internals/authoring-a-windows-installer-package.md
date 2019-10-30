---
title: Windows インストーラーパッケージを作成する |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- .msi files, VSPackages
- msi files, VSPackages
ms.assetid: 0ce7c21d-0d3f-47fe-a0bb-eed506e32609
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: aa967b5f23ff9f4e5afa67b9b1cb4e83707616c6
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72982227"
---
# <a name="author-a-windows-installer-package"></a>Windows インストーラーパッケージを作成する
データは Windows インストーラーモデルを駆動します。 たとえば、ファイルをコピーしてレジストリエントリを書き込むための手続き型スクリプトを記述するのではなく、ファイルとレジストリデータを格納するデータベーステーブルの行と列を作成します。

## <a name="database-entries"></a>データベースエントリ
VSPackage をインストールするには、Windows インストーラーパッケージに次のタスクを実行するためのデータベースエントリが含まれている必要があります。

- システムを検索して、VSPackage がサポートしている [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] のバージョンを探します (AppSearch、CompLocator、RegLocator、DrLocator、署名を含むテーブル Windows インストーラーを使用します)。

- サポートされているバージョンの [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] がインストールされていない場合、または VSPackage の別のシステム要件 (LaunchCondition テーブルを使用) が満たされていない場合は、インストールをキャンセルします。

- ディレクトリ、コンポーネント、およびファイルテーブルを使用して、VSPackage ファイルと依存ファイルをインストールします。

- VSPackage の適切な情報をレジストリに追加します (レジストリテーブルを使用します)。

- **Devenv.exe/セットアップ**を呼び出して (CustomAction テーブルを使用して) [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] の VSPackage を統合します。

詳細については、「 [Windows インストーラー](/windows/desktop/Msi/windows-installer-portal)」を参照してください。

## <a name="setup-tools"></a>セットアップツール
さまざまなサードパーティ製セットアップツールは、Windows インストーラーパッケージの開発環境を提供します。 次の無料ツールを利用できます。

- InstallShield 制限付きエディション

   Visual Studio の **[新しいプロジェクト]** ダイアログボックスでは、InstallShield の限定バージョンを取得できます。 **[その他のプロジェクトの種類]** を展開し、 **[セットアップと配置]** を選択します。 InstallShield テンプレートを選択します。

- Windows インストーラー XML ツールセット

   Windows インストーラー XML (WiX) ツールセットは、XML ソースファイルからパッケージを Windows インストーラービルドします。 WiX ツールセットは、Microsoft オープンソースプロジェクトです。 [Wix ツールセット](https://sourceforge.net/projects/wix/)からソースコードと実行可能ファイルをダウンロードできます。

   [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]を使用して [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] に統合される商用製品の場合は、「 [Visual Studio Marketplace](https://marketplace.visualstudio.com/)」を参照してください。

## <a name="see-also"></a>関連項目
- [Windows インストーラーと共に Vspackage をインストールする](../../extensibility/internals/installing-vspackages-with-windows-installer.md)