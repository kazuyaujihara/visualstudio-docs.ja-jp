---
title: -UseEnv (devenv.exe)
ms.date: 01/10/2019
ms.topic: reference
f1_keywords:
- VC.Project.UseEnvVars.ExcludePath
- VC.Project.UseEnvVars.LibraryPath
- VC.Project.UseEnvVars.SourcePath
- VC.Project.UseEnvVars.Include
- VC.Project.UseEnvVars.Path
- VC.Project.UseEnvVars.ReferencePath
helpviewer_keywords:
- UseEnv switch
- /UseEnv Devenv switch
- Devenv, /UseEnv
ms.assetid: 2dd14603-a61b-42d2-ba31-427a0ee8a799
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 37326bbe44eed15a562f0d28c01eac02973a2487
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62789259"
---
# <a name="useenv-devenvexe"></a>/UseEnv (devenv.exe)

Visual Studio を起動し、コンパイルのための特定の環境変数を読み込みます。

> [!NOTE]
> このスイッチは、**C++ によるデスクトップ開発**ワークロードと共にインストールされます。

## <a name="syntax"></a>構文

```shell
devenv /UseEnv {SolutionName|ProjectName}
```

## <a name="arguments"></a>引数

- *SolutionName*

  ソリューション ファイルの完全パスと名前。

- *ProjectName*

  プロジェクト ファイルの完全パスと名前。

## <a name="remarks"></a>解説

このスイッチは、Visual Studio IDE の **[VC++ ディレクトリ]** のプロジェクト プロパティに影響します。 `/UseEnv` スイッチを指定した場合、**[VC++ ディレクトリ]** ノードに PATH、INCLUDE、LIBPATH、および LIB 環境変数の値が表示されます (**[ソース ディレクトリ]** と **[除外ディレクトリ]** の値も表示されます)。それ以外の場合、このノードでは環境変数が 5 つのディレクトリ値**実行可能ファイル ディレクトリ**、**インクルード ディレクトリ**、**参照ディレクトリ**、**ライブラリ ディレクトリ**、**ライブラリ WinRT ディレクトリ**に置き換えられます

> [!TIP]
> プロジェクトのプロパティにアクセスするには、C++ プロジェクトを右クリックして **[プロパティ]** を選択します。 **[プロパティ ページ]** ダイアログ ボックスで、**[構成プロパティ]** を選択してから **[VC++ ディレクトリ]** を選択します。

このスイッチでプロジェクト名を指定すると、プロジェクトの親ソリューション内のすべてのプロジェクトの環境変数が表示されます。

## <a name="example"></a>例

次の例では、Visual Studio を起動し、環境変数を `MySolution` ソリューションのプロパティ ページに読み込みます。

```shell
devenv.exe /useenv "%USERPROFILE%\source\repos\MySolution\MySolution.sln"
```

## <a name="see-also"></a>関連項目

- [Devenv コマンドライン スイッチ](../../ide/reference/devenv-command-line-switches.md)
- [[VC++ ディレクトリ] プロパティ ページ (Windows)](/cpp/ide/vcpp-directories-property-page)
