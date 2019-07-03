---
title: パラメーターの生成リファクタリング
ms.date: 06/19/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: e95e76c35afdb8cdbe38c8b33329734ba68361b1
ms.sourcegitcommit: 7eb2fb21805d92f085126f3a820ac274f2216b4e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2019
ms.locfileid: "67329074"
---
# <a name="generate-parameter"></a>パラメーターを生成する

このリファクタリングは以下に適用されます。

- C#

**概要:** メソッドのパラメーターを自動的に生成します。

**条件:** 現在のコンテキストに存在しないメソッドの変数を参照し、エラーを受け取ります。コード修正としてパラメーターを生成できます。 

**理由:** コンテキストを失わずに、メソッドのシグネチャをすばやく変更できます。

## <a name="how-to"></a>方法

1. 変数名内にカーソルを置き、**Ctrl** + **.** キーを押して、 **[クイック アクションとリファクタリング]** メニューをトリガーします。
1. **[Generate parameter]\(パラメーターを生成する\)** を選択します。

   ![パラメーターを生成する](media/generate-parameter.png) 

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)
