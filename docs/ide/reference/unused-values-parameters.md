---
title: 使用されていない値とパラメーター
ms.date: 02/15/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: afcf85fff188853890b86cf7deb13b2457f5e0b8
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58157699"
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
