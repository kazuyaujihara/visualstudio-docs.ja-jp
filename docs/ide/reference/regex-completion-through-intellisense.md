---
title: IntelliSense メニューを使用した正規表現の入力
ms.date: 06/10/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 75110432f9bba35ce02588032b9a41dece01056b
ms.sourcegitcommit: 91c7f1b525e0c22d938bc4080ba4ceac2483474f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67033423"
---
# <a name="regex-completion-through-intellisense-menu"></a>IntelliSense メニューを使用した正規表現の入力

このリファクタリングは以下に適用されます。

- C#

**概要:** IntelliSense メニューを使用して正規表現 (regex) を入力します。

**条件:** IntelliSense を使用して正規表現を記述します。 IntelliSense によって、基本入力と、各正規表現文字の説明が示されます。 

**理由:** 正規表現の記述は簡単ではありませんが、IntelliSense を使用することで楽に記述できます。

## <a name="how-to"></a>方法

1. 正規表現文字列にカーソルを置きます。
2. **Ctrl** + **Space** キーを押して、**IntelliSense** メニューを表示します。
3. 正規表現文字列を追加する文字を選択します。

   ![IntelliSense を使用した正規表現の入力](../media/regex-completion-intellisense.png)

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)
