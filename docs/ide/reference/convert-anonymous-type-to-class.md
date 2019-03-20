---
title: 匿名型をクラスに変換する
ms.date: 02/13/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: f29e31fb87d8b18e7f5a46d16f90217ee08d51f6
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58154583"
---
# <a name="convert-anonymous-type-to-class"></a>匿名型をクラスに変換する

このリファクタリングは以下に適用されます。

- C#

**概要:** 匿名型をクラスに変換します。

**条件:** クラスに組み込みたい匿名型がある場合です。

**理由:** 匿名型は、それをローカルで使用しているときのみ便利です。 コードが長くなった場合、それをクラスに昇格させる簡単な方法があると便利なためです。

## <a name="how-to"></a>方法

1. 匿名型の上にカーソルを置きます。
2. 行の任意の場所で **Ctrl**+**.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。

   ![匿名型をクラスに変換する](media/convert-anon-to-class.png)

2. **Enter** キーを押して、リファクタリングを受け入れます。

   ![受け入れられた匿名型のクラスへの変換](media/convert-anon-to-class-complete.png)

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)
