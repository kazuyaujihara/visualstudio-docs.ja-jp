---
title: 使用されていない値とパラメーター
ms.date: 02/15/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 1ea80887fff6dcb1afba80feb782b23d1e790579
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57325027"
---
# <a name="unused-expression-values-and-parameters"></a>使用されていない式の値とパラメーター

このリファクタリングは以下に適用されます。

- C#
- Visual Basic

**概要:** 使用されていないパラメーターをフェードアウトし、使用されていない式の値に警告を生成します。

**条件:** まったく使用されていないパラメーターや式の値があります。

**理由:** 値やパラメーターが使用されなくなったかどうかを判断するのは難しい場合があります。 そのような値をフェードアウトするか警告を出すことで、削除するコードが視覚的にわかりやすくなります。

## <a name="unused-expression-values-and-parameters-diagnostic"></a>使用されていない式の値とパラメーターの診断

1. 使用されていない式の値やパラメーターがあります。
2. 使用されていないパラメーターがフェードアウトしているように表示されます。使用されていない式の値が警告を受け取ります。

  ![使用されていないパラメーター](media/unused-parameter.png)
  ![使用されていない値](media/unused-value.png)

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)
- [.NET 開発者向けのヒント](../../ide/visual-studio-2017-for-dotnet-developers.md)
