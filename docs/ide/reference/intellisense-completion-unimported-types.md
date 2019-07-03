---
title: インポートされていない型に対する IntelliSense 入力候補
description: '`using` ディレクティブでまだインポートしていない型に対して IntelliSense 入力候補を使用する方法です。'
ms.date: 06/20/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: f313cfa8520e4c13b310be0f9223466c529ca18f
ms.sourcegitcommit: 16bcaca215de75479695738d3c2d703c78c3500e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2019
ms.locfileid: "67312925"
---
# <a name="intellisense-completion-for-unimported-types"></a>インポートされていない型に対する IntelliSense 入力候補

このリファクタリングは以下に適用されます。

- C#

**概要:** IntelliSense で、インポートされていない型に対して入力候補を提供します。

**条件:** プロジェクト内に既に依存関係はあっても、インポート ステートメントがファイルにまだ追加されていない型を、追加する必要があります。 

**理由:** インポート ステートメントをファイルに手動で追加する必要はありません。

## <a name="how-to"></a>方法

1. プロジェクト内に依存関係のある型を使い始めると、IntelliSense で提案が提供されます。
2. **Tab** キーを押します。 

   インポート ステートメントがファイルに追加されます。

   ![インポートされていない型に対する IntelliSense 入力候補](media/intellisense-completion-unimported-types.png)

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)
