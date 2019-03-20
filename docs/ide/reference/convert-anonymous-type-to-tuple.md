---
title: 匿名型をタプルに変換する
ms.date: 02/13/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: b6f5dd8e53ed2e0695370a1cdcb837609be30035
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58154440"
---
# <a name="convert-anonymous-type-to-tuple"></a>匿名型をタプルに変換する

このリファクタリングは以下に適用されます。

- C#

**概要:** 匿名型をタプルに変換します。

**条件:** タプルの資格を満たす匿名型があります。

**理由:**[タプル](/dotnet/csharp/tuples)は構文を軽量に保つのに便利です。 このクイック アクションにより、この C# 機能が利用しやすくなります。

## <a name="how-to"></a>方法

1. 匿名型の上にカーソルを置きます。
2. 行の任意の場所で **Ctrl**+**.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。

   ![匿名型をタプルに変換する](media/convert-anon-to-tuple.png)

2. **Enter** キーを押して、リファクタリングを受け入れます。

   ![匿名型をタプルに変換する](media/convert-anon-to-tuple-complete.png)

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)
