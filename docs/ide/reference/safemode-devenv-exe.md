---
title: -SafeMode (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 14b2ac3a80a9e17e0c554f56ae8e31ac32450c5e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62945480"
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)

Visual Studio をセーフ モードで起動し、既定の環境とサービスのみを読み込みます。

## <a name="syntax"></a>構文

```shell
devenv /SafeMode
```

## <a name="remarks"></a>解説

このスイッチでは、Visual Studio が起動したときに、すべてのサード パーティ VSPackage を読み込まないようにするため、実行が安定したものになります。

## <a name="example"></a>例

次の例では、Visual Studio をセーフ モードで起動します。

```shell
devenv /safemode
```

## <a name="see-also"></a>関連項目

- [Devenv コマンドライン スイッチ](../../ide/reference/devenv-command-line-switches.md)