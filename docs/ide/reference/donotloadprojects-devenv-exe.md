---
title: -DoNotLoadProjects (devenv.exe)
ms.date: 03/11/2019
ms.topic: reference
helpviewer_keywords:
- Devenv, /DoNotLoadProjects switch
- /DoNotLoadProjects Devenv switch
- DoNotLoadProjects Devenv switch
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 91c4da26d202e1a23ff70a7c655f64fd6c05a340
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57875395"
---
# <a name="donotloadprojects-devenvexe"></a>/DoNotLoadProjects (devenv.exe)

プロジェクトを読み込むことなく、指定したソリューションを開きます。

## <a name="syntax"></a>構文

```shell
devenv /DoNotLoadProjects SolutionName
```

## <a name="arguments"></a>引数

- *SolutionName*

  必須です。 開くソリューションの完全パスと名前。

## <a name="example"></a>例

この例では、プロジェクトを読み込むことなく、ソリューション MySln.sln を開きます。

```shell
devenv /donotloadprojects MySln.sln

```

## <a name="see-also"></a>関連項目

- [Devenv コマンドライン スイッチ](../../ide/reference/devenv-command-line-switches.md)
