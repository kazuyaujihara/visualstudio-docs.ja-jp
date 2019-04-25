---
title: ラムダ式またはブロックの本体の使用
ms.date: 02/14/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 1f055925a4da916bf88da802e7a4991b0362b057
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62789441"
---
# <a name="use-expression-body-or-block-body-for-lambda-expressions"></a>ラムダ式に式の本体またはブロックの本体を使用する

このリファクタリングは以下に適用されます。

- C#

**概要:** 式の本体またはブロックの本体を使用するためにラムダ式をリファクタリングできます。

**条件:** 式の本体またはブロックの本体を使用するためにラムダ式を使用します。 

**理由:** ラムダ式リファクタリングすることで、ユーザー設定に基づいて読みやすさを向上させることができます。

## <a name="lambda-expression-body-or-block-body-refactoring"></a>ラムダ式の式本体またはブロック本体のリファクタリング

1. ラムダ演算子の右にカーソルを置きます。
2. 行の任意の場所で **Ctrl**+**.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。

  ![ラムダ式/ブロック本体の使用](media/block-body-lambda.png)

3. **[Use block body for lambda expressions]\(ラムダ式にブロックの本体を使用する\)** または **[Use expression body for lambda expressions]\(ラムダ式に式の本体を使用する\)** を選択します。

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)
- [.NET 開発者向けのヒント](../../ide/visual-studio-2017-for-dotnet-developers.md)