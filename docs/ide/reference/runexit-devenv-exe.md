---
title: -RunExit (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- RunExit Devenv switch
- Devenv, /RunExit switch
- /RunExit Devenv switch
ms.assetid: bfc94875-5fc0-4110-b961-d59c0b403790
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3fa010e72267dadfb1974f7ce8be3b6b9a3e1cff
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62935048"
---
# <a name="runexit-devenvexe"></a>/RunExit (devenv.exe)

指定したプロジェクトまたはソリューションをコンパイルおよび実行してから、統合開発環境 (IDE) を閉じます。

## <a name="syntax"></a>構文

```shell
devenv /RunExit {SolutionName|ProjectName} [/Out OutputFilename]
```

## <a name="arguments"></a>引数

- *SolutionName*

  ソリューション ファイルの完全パスと名前。

- *ProjectName*

  プロジェクト ファイルの完全パスと名前。

- `/Out` *OutputFilename*

  任意。 ツールの出力を送信する先のファイル名。 このファイルが既に存在する場合、ファイルの末尾に出力が追加されます。

## <a name="remarks"></a>解説

アクティブなソリューション構成に対して指定された設定に従って、指定したプロジェクトまたはソリューションをコンパイルして実行します。 このスイッチを指定すると、プロジェクトまたはソリューションの実行中に IDE が最小化されます。 プロジェクトまたはソリューションの実行が完了すると、IDE は閉じられます。

- 空白を含む文字列を二重引用符で囲みます。

- エラーなどの概要情報は、**[コマンド]** ウィンドウ、または `/Out`スイッチで指定した任意のログ ファイルに表示できます。

## <a name="example"></a>例

この例では、アクティブな配置構成を使用し、IDE を最小化した状態でソリューション `MySolution` を実行してから IDE を閉じます。

```
devenv /runexit "%USERPROFILE%\source\repos\MySolution\MySolution.sln"
```

## <a name="see-also"></a>関連項目

- [Devenv コマンドライン スイッチ](../../ide/reference/devenv-command-line-switches.md)
- [/Run (devenv.exe)](../../ide/reference/run-devenv-exe.md)
- [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)