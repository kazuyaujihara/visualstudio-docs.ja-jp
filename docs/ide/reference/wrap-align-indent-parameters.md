---
title: ラップ、インデント、パラメーターの整列
ms.date: 02/13/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 9c17d5c9d6874c836954941e1fccd8ce9d9f2e3a
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58149264"
---
# <a name="wrap-indent-and-align-parameters"></a>ラップ、インデント、およびパラメーターの整列

このリファクタリングは以下に適用されます。

- C#

- Visual Basic

**概要:** ラップ、インデント、およびパラメーターの整列が可能です。

**条件:** 複数のパラメーターがあるメソッド宣言または呼び出しがある場合です。

**理由:** ユーザー設定に従ってラップまたはインデントされていると、長いパラメーターの一覧に目を通すときに便利です。

## <a name="how-to"></a>方法

1. パラメーター一覧にカーソルを置きます。
2. 行の任意の場所で **Ctrl**+**.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。

   ![ラップ、インデント、およびパラメーターの整列](media/wrap-parameters.png)

3. **Enter** キーを押して、リファクタリングを受け入れます。

   ![適用されたラップ、インデント、およびパラメーターの整列](media/wrap-parameters-completed.png)

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)
