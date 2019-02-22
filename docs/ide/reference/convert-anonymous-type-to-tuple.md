---
title: 匿名型をタプルに変換する
ms.date: 02/13/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: b7a53aa8f329c1cdedc0cedff7e56b3f6dfa2f2a
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335824"
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
