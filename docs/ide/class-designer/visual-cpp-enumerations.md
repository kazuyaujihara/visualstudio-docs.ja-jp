---
title: クラス デザイナーの C++ 列挙体
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], enumerations
ms.assetid: 11e90ba1-18cd-44f8-9e26-e3746a7a19d1
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: a514d5eb4b7f79e2fd193c79de670b6dd9c14cb5
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72747987"
---
# <a name="c-enumerations-in-class-designer"></a>クラス デザイナーの C++ 列挙体

**クラス デザイナー**では、C++ の `enum`、およびスコープを持つ `enum class` 型はサポートされていません。 例を次に示します。

```cpp
enum CardSuit {
   Diamonds = 1,
   Hearts = 2,
   Clubs = 3,
   Spades = 4
};

// or...
enum class CardSuit {
   Diamonds = 1,
   Hearts = 2,
   Clubs = 3,
   Spades = 4
};
```

クラス ダイアグラムにおける C++ 列挙体の図形の形状と動作は構造体の図形に似ていますが、ラベルが **[Enum]** または **[Enum class]** である点と、青ではなくピンクである点、および左と上の余白に色つきの枠がある点が異なります。 列挙体の図形も構造体の図形も、角が直角になっています。

`enum` 型の使用法の詳細については、「[列挙型](/cpp/cpp/enumerations-cpp)」を参照してください。

## <a name="see-also"></a>関連項目

- [C++ のコードを操作する](working-with-visual-cpp-code.md)
- [列挙型](/cpp/cpp/enumerations-cpp)