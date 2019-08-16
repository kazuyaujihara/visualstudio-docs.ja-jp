---
title: SetCurrentThread コマンド
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- debug.setcurrentthread
helpviewer_keywords:
- Set Current Thread command
- Debug.SetCurrentThread command
ms.assetid: 9917ed1d-6c30-4d94-b2f0-69acce74f1b2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3ea652f04295871f9437d80555254caecab87a48
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68926060"
---
# <a name="set-current-thread-command"></a>SetCurrentThread コマンド
指定したスレッドを現在のスレッドとして設定します。

## <a name="syntax"></a>構文

```
Debug.SetCurrentThread index
```

## <a name="arguments"></a>引数
`index`

必須です。 スレッドをそのインデックスで選択します。

## <a name="example"></a>例

```
>Debug.SetCurrentThread 1
```

## <a name="see-also"></a>関連項目

- [Visual Studio のコマンド](../../ide/reference/visual-studio-commands.md)
- [コマンド ウィンドウ](../../ide/reference/command-window.md)
- [検索コマンド ボックス](../../ide/find-command-box.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)
