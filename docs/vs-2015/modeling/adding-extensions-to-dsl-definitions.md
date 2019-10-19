---
title: DSL 定義への拡張機能の追加 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 07e133be-92ab-4936-a02b-45d2012bd0a6
caps.latest.revision: 8
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 447001a8aefa22fe15bce9158eddeb0cdb26e4e8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72654718"
---
# <a name="adding-extensions-to-dsl-definitions"></a>DSL 定義への拡張機能の追加
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

DSL 定義の拡張機能を使用すると、ドメイン固有言語 (DSL) に対する拡張機能のパッケージを作成できます。 DSL 拡張機能は、Visual Studio Integration Extension (VSIX) に含まれており、DSL と同じ方法でユーザーのコンピューターにインストールできます。 その他の機能は、実行時に動的に有効にしたり無効にしたりすることができます。 Dsl は拡張用に明示的に設計する必要はなく、拡張 DSL を変更することなく、後またはサードパーティが拡張することができます。

 追加機能には、次のものが含まれます。

- モデル要素とプレゼンテーション要素のプロパティ

- 図形とコネクタのデコレーター

- クラス、リレーションシップ、図形、およびコネクタ

- 検証制約

- ツールボックスの項目とタブ

  拡張 DSL のユーザーは、追加機能のインスタンスを含むモデルを作成して保存できます。また、適切な拡張機能をインストールした他のユーザーがそれらを読み取ることができます。 拡張機能をインストールしていないユーザーは、追加機能を使用できませんが、追加の機能を失うことなく、モデルを更新して保存することができます。

  サンプルコードとこの機能の詳細については、「 [Visual Studio の視覚化とモデリング SDK](http://go.microsoft.com/fwlink/?LinkID=186128) 」 Web サイトを参照してください。

## <a name="see-also"></a>参照
 [Visual Studio の視覚化およびモデリング SDK](http://go.microsoft.com/fwlink/?LinkID=186128)
