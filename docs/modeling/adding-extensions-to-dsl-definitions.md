---
title: DSL 定義への拡張機能の追加
ms.date: 11/04/2016
ms.topic: conceptual
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f3e44c79783479c46247e4026788725d6ae16da7
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72747652"
---
# <a name="add-extensions-to-dsl-definitions"></a>DSL 定義に拡張機能を追加する

DSL 定義の拡張機能を使用すると、ドメイン固有言語 (DSL) に対する拡張機能のパッケージを作成できます。 DSL 拡張機能は、Visual Studio Integration Extension (VSIX) に含まれており、DSL と同じ方法でユーザーのコンピューターにインストールできます。 その他の機能は、実行時に動的に有効にしたり無効にしたりすることができます。 Dsl は拡張用に明示的に設計する必要はなく、拡張 DSL を変更することなく、後で、またはサードパーティが拡張できます。

DSL 拡張には、次の機能を含めることができます。

- モデル要素とプレゼンテーション要素のプロパティ

- 図形とコネクタのデコレーター

- クラス、リレーションシップ、図形、およびコネクタ

- 検証制約

- ツールボックスの項目とタブ

拡張 DSL のユーザーは、追加機能のインスタンスを含むモデルを作成して保存できます。 モデルは、適切な拡張機能をインストールした他のユーザーが読み取ることができます。 拡張機能をインストールしていないユーザーは、追加機能を使用できませんが、追加の機能を失うことなく、モデルを更新して保存することができます。

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>関連項目

- [関連するブログの投稿](https://devblogs.microsoft.com/devops/the-visual-studio-modeling-sdk-is-now-available-with-visual-studio-2017/)
