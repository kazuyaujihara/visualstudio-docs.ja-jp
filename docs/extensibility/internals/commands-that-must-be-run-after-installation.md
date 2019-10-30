---
title: インストール後に実行する必要があるコマンド |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- post-install commands
ms.assetid: c9601f2e-2c6e-4da9-9a6e-e707319b39e2
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7e85a03c71064687fdfbacf24b7aa59cd2a47f1a
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72982019"
---
# <a name="commands-that-must-be-run-after-installation"></a>インストール後に実行する必要があるコマンド
*.Msi*ファイルを使用して拡張機能を展開する場合は、Visual Studio で拡張機能を検出するために、インストールの一部として**devenv/setup**を実行する必要があります。

> [!NOTE]
> このトピックの情報は、Visual Studio 2008 以前のバージョンで*devenv.exe*を検索する場合に適用されます。 新しいバージョンの Visual Studio で*devenv.exe*を検出する方法については、「[システム要件の検出](../../extensibility/internals/detecting-system-requirements.md)」を参照してください。

## <a name="find-devenvexe"></a>Devenv.exe を検索する
 各バージョンの*devenv.exe*をレジストリ値から検索して [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] インストーラーによって書き込まれます。 reglocator テーブルと AppSearch テーブルを使用して、レジストリ値をプロパティとして格納します。 詳細については、「[システム要件の検出](../../extensibility/internals/detecting-system-requirements.md)」を参照してください。

### <a name="reglocator-table-rows-to-locate-devenvexe-from-different-versions-of-visual-studio"></a>異なるバージョンの Visual Studio から devenv.exe を検索するための RegLocator テーブル行

|署名|ルート|キー|名|[種類]|
|-----------------|----------|---------|----------|----------|
|RL_DevenvExe_2002|2|SOFTWARE\Microsoft\VisualStudio\7.0\Setup\VS|環境パス|2|
|RL_DevenvExe_2003|2|SOFTWARE\Microsoft\VisualStudio\7.1\Setup\VS|環境パス|2|
|RL_DevenvExe_2005|2|SOFTWARE\Microsoft\VisualStudio\8.0\Setup\VS|環境パス|2|
|RL_DevenvExe_2008|2|SOFTWARE\Microsoft\VisualStudio\9.0\Setup\VS|環境パス|2|

### <a name="appsearch-table-rows-for-corresponding-reglocator-table-rows"></a>AppSearch 対応する RegLocator テーブル行のテーブル行

|property|署名|
|--------------|-----------------|
|DEVENV_EXE_2002|RL_DevenvExe_2002|
|DEVENV_EXE_2003|RL_DevenvExe_2003|
|DEVENV_EXE_2005|RL_DevenvExe_2005|
|DEVENV_EXE_2008|RL_DevenvExe_2008|

 たとえば、Visual Studio インストーラーは、 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0\Setup\VS\EnvironmentPath**のレジストリ値を*C:\VS2008\Common7\IDE\devenv.exe*として書き込みます。これは、実行可能ファイルへの完全なパスです。インストーラーを実行する必要があります。

> [!NOTE]
> RegLocator テーブルの Type 列は2であるため、署名テーブルで追加のバージョン情報を指定する必要はありません。

## <a name="run-devenvexe"></a>Devenv.exe を実行します。
 AppSearch standard アクションがインストーラーで実行されると、AppSearch テーブル内の各プロパティの値が、対応するバージョンの Visual Studio の*devenv.exe*ファイルをポイントします。 指定したレジストリ値が存在しない場合は、そのバージョンの Visual Studio がインストールされていないため、指定したプロパティは null に設定されます。

 Windows インストーラーは、カスタム動作の種類50を通じてプロパティが指す実行可能ファイルの実行をサポートしています。 カスタム動作には、VSPackage が正常にインストールされていることを確認するために、スクリプト内実行 `msidbCustomActionTypeInScript` オプション (1024) と `msidbCustomActionTypeCommit` (512) が含まれている必要があります。これにより、が [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]に統合されます。 詳細については、「 [CustomAction table](/windows/desktop/msi/customaction-table) 」および「 [Custom action in-script execution options](/windows/desktop/msi/custom-action-in-script-execution-options)」を参照してください。

 種類が50のカスタムアクションでは、実行可能ファイルを含むプロパティを、ターゲット列のソース列とコマンドライン引数の値として指定します。

### <a name="customaction-table-rows-to-run-devenvexe"></a>CustomAction を実行するテーブルの行を実行します。

|操作|[種類]|[ソース]|Target|
|------------|----------|------------|------------|
|CA_RunDevenv2002|1586|DEVENV_EXE_2002|/setup|
|CA_RunDevenv2003|1586|DEVENV_EXE_2003|/setup|
|CA_RunDevenv2005|1586|DEVENV_EXE_2005|/setup|
|CA_RunDevenv2008|1586|DEVENV_EXE_2008|/setup|

 インストール中に実行するようにスケジュールを設定するには、カスタムアクションを InstallExecuteSequence テーブルに作成する必要があります。 このバージョンの [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] がシステムにインストールされていない場合、カスタムアクションが実行されないようにするには、条件列の各行で対応するプロパティを使用します。

> [!NOTE]
> Null 値プロパティは、条件で使用した場合に `False` に評価されます。

 各カスタムアクションのシーケンス列の値は、Windows インストーラーパッケージ内の他のシーケンス値によって異なります。 Ccmsetup.exe*カスタムアクションが*installfinalize 標準アクションの直前にできるだけ近くに実行されるように、シーケンス値を指定する必要があります。

### <a name="installexecutesequence-table-to-schedule-the-devenvexe-custom-actions"></a>Devenv.exe のカスタムアクションをスケジュールするための InstallExecuteSequence テーブル

|操作|条件|シーケンス|
|------------|---------------|--------------|
|CA_RunDevenv2002|DEVENV_EXE_2002|6602|
|CA_RunDevenv2003|DEVENV_EXE_2003|6603|
|CA_RunDevenv2005|DEVENV_EXE_2005|6605|
|CA_RunDevenv2008|DEVENV_EXE_2008|6608|

## <a name="see-also"></a>関連項目
- [Windows インストーラーと共に Vspackage をインストールする](../../extensibility/internals/installing-vspackages-with-windows-installer.md)