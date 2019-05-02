---
title: タスク コメント
description: コードにタスク コメントを追加する
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 562DCB46-D8FA-4DC4-AAEA-F274448C4CD2
ms.openlocfilehash: 3caef73ba46afd8eaf90826540248cb2d5c4efef
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62999729"
---
# <a name="task-comments"></a>タスク コメント

コードを記述する場合、完了していないコード、問題があるコード、警告の簡単な回避策などをコメントで明示的に示すのは標準的な方法です。 Visual Studio for Mac に用意されている既定の指示トークンは、TODO、HACK、FIXME、および UNDONE です。 カスタマイズしたトークンは、次の図のように、**[Visual Studio]、[ユーザー設定]、[環境]、[タスク]** の順に選択して定義できます。

![タスク一覧のユーザー設定](media/source-editor-image10.png)

新しいタスク コメントを追加するには、タスク キーワードを含むコメントを追加します。 次に例を示します。

```csharp
//TODO: Finish this for all properties.
```

Visual Studio for Mac では、これらのマーカーに注意を引くために、**タスク一覧**パッドでマーカーが強調表示されます。これは、**[表示] > [パッド] > [タスク]** に移動することで表示できます。

![タスク一覧パッド](media/source-editor-image11.png)

## <a name="see-also"></a>関連項目

- [タスク一覧の使用 (Windows の Visual Studio)](/visualstudio/ide/using-the-task-list)