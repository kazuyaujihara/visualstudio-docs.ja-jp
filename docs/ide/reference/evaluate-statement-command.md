---
title: EvaluateStatement
ms.date: 02/25/2019
ms.topic: reference
f1_keywords:
- debug.evaluatestatement
helpviewer_keywords:
- Debug.EvaluateStatement command
- Evaluate Statement command
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c7eff96d1b413ea10b1274eb7d7938148727acbc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62790877"
---
# <a name="evaluate-statement-command"></a>Evaluate Statement コマンド

指定したステートメントを評価し、表示します。

## <a name="syntax"></a>構文

```cmd
>Debug.EvaluateStatement text
```

## <a name="arguments"></a>引数

`text`

必須です。 評価するステートメント。

## <a name="example"></a>例

```cmd
>Debug.EvaluateStatement args.Length
```

## <a name="see-also"></a>関連項目

- [Print コマンド](../../ide/reference/print-command.md)
- [Visual Studio のコマンド](../../ide/reference/visual-studio-commands.md)
- [コマンド ウィンドウ](../../ide/reference/command-window.md)
- [検索コマンド ボックス](../../ide/find-command-box.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)