---
title: -DoNotLoadProjects (devenv.exe)
ms.date: 04/30/2019
ms.topic: reference
helpviewer_keywords:
- Devenv, /DoNotLoadProjects switch
- /DoNotLoadProjects Devenv switch
- DoNotLoadProjects Devenv switch
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 34fe7dfed2774eace7d32b1c9041355b566d4e76
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72654492"
---
# <a name="donotloadprojects-devenvexe"></a>/DoNotLoadProjects (devenv.exe)

**Visual Studio 2019 バージョン 16.1 の新機能**

プロジェクトを読み込むことなく、指定したソリューションを開きます。 詳細については、「[Visual Studio のフィルター処理済みソリューション](../filtered-solutions.md)」をご覧ください。

## <a name="syntax"></a>構文

```shell
devenv /DoNotLoadProjects SolutionName
```

## <a name="arguments"></a>引数

*SolutionName*

必須です。 開くソリューションの完全パスと名前。

## <a name="example"></a>例

この例では、プロジェクトを読み込むことなく、ソリューション MySln.sln を開きます。

```shell
devenv /donotloadprojects MySln.sln
```

## <a name="see-also"></a>関連項目

- [Visual Studio のフィルター処理済みソリューション](../filtered-solutions.md)
- [Devenv コマンドライン スイッチ](../../ide/reference/devenv-command-line-switches.md)
