---
title: 匿名型をクラスに変換する
ms.date: 02/13/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: e3613f365b2510111f6854087a597df387ab1a4c
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335835"
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
