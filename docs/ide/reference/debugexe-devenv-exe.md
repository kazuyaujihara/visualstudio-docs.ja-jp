---
title: -DebugExe (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- Devenv, /DebugExe switch
- DebugExe switch
- /DebugExe [devenv.exe]
- debugging executables
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 05266a6f1b5ee0be22e2edc8df1c03b720844f4f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62968081"
---
# <a name="debugexe-devenvexe"></a>/DebugExe (devenv.exe)

指定したデバッグ対象の実行可能ファイルを開きます。

## <a name="syntax"></a>構文

```shell
devenv /DebugExe ExecutableFile
```

## <a name="arguments"></a>引数

- *ExecutableFile*

  必須です。 `.exe` ファイルのパスとファイル名。 `.exe` ファイルが見つからない場合、または存在しない場合、警告やエラーは表示されず、Visual Studio は通常どおり起動します。

## <a name="remarks"></a>解説

*ExecutableFile* パラメーターに続くどの文字列もそのファイルに引数として渡されます。

## <a name="example"></a>例

次の例では、デバッグするために `MyApplication.exe` ファイルを開きます。

```shell
devenv /debugexe MyApplication.exe
```

## <a name="see-also"></a>関連項目

- [Devenv コマンドライン スイッチ](../../ide/reference/devenv-command-line-switches.md)