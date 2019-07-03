---
title: switch ステートメントを switch 式に変換する
ms.date: 06/19/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: ecb7750301101a2607c17e68b5e919623a03caba
ms.sourcegitcommit: 7eb2fb21805d92f085126f3a820ac274f2216b4e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2019
ms.locfileid: "67329064"
---
# <a name="convert-switch-statement-to-switch-expression"></a>switch ステートメントを switch 式に変換する

このリファクタリングは以下に適用されます。

- C#

**概要:** [switch ステートメント](/dotnet/csharp/language-reference/keywords/switch)を C# 8.0 の [switch 式](/dotnet/csharp/whats-new/csharp-8#switch-expressions)に変換します。

**条件:** `switch` ステートメントを `switch` 式に、またはその逆に変換します。 

**理由:** 式だけを使っている場合、このリファクタリングにより、従来の `switch` ステートメントから簡単に移行できます。

## <a name="how-to"></a>方法

1. `switch` 式は C# 8.0 の新しい機能であるため、プロジェクト ファイルで、[言語バージョンをプレビューに設定](/dotnet/csharp/language-reference/configure-language-version#set-the-language-version-in-visual-studio)します。
2. `switch` キーワード内にカーソルを置き、**Ctrl** + **.** キーを押して、 **[クイック アクションとリファクタリング]** メニューをトリガーします。
3. **[Convert switch statement to expression]\(switch ステートメントを式に変換する\)** を選択します。

   ![switch ステートメントを switch 式に変換する](media/convert-switch-statement-to-switch-expression.png) 

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)
