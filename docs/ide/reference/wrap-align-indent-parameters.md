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
ms.openlocfilehash: ccdf29e3a4cda2bf5d527a2b712878c1fbd76197
ms.sourcegitcommit: cd21b38eefdea2cdefb53e68e7a30b868e78dd6b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2019
ms.locfileid: "66037580"
---
# <a name="wrap-indent-and-align-parameters-or-arguments"></a>ラップ、インデント、およびパラメーターまたは引数の整列

このリファクタリングは以下に適用されます。

- C#

- Visual Basic

**概要:** ラップ、インデント、およびパラメーターまたは引数の整列を行えます。

**条件:** 複数のパラメーターまたは引数があるメソッド宣言または呼び出しがある場合です。

**理由:** ユーザー設定に従ってラップまたはインデントされていると、パラメーターまたは引数の長い一覧に目を通すときに便利です。

## <a name="how-to"></a>方法

1. パラメーター一覧にカーソルを置きます。
2. 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。

   ![ラップ、インデント、およびパラメーターの整列](media/wrap-parameters.png)

3. **Enter** キーを押して、リファクタリングを受け入れます。

   ![適用されたラップ、インデント、およびパラメーターの整列](media/wrap-parameters-completed.png)

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)
