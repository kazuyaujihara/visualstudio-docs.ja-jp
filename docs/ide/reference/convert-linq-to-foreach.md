---
title: LINQ クエリを foreach ステートメントに変換するためのコードのリファクタリング
description: クエリ構文で記述された LINQ クエリを foreach ステートメントに変換します。
ms.date: 05/15/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 446d0f3a4988552e8e1fbbac32ca150491975d94
ms.sourcegitcommit: 0f5f7955076238742f2071d286ad8e896f3a6cad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2019
ms.locfileid: "68483685"
---
# <a name="refactoring-to-convert-linq-to-a-foreach-statement"></a>LINQ を foreach ステートメントに変換するためのリファクタリング

このリファクタリングは、[LINQ クエリ構文](/dotnet/csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq)を [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) ステートメントに変換するために使います。

このリファクタリングは以下に適用されます。

- C#

## <a name="how-to-use-it"></a>使用方法

1. `from` で始まる LINQ クエリ全体を選びます。

   > [!NOTE]
   > このリファクタリングは、クエリ構文で表されている LINQ クエリの変換にのみ使用でき、メソッド構文には使用できません。

1. 行の任意の場所で **Ctrl**+ **.** キーを押すと、 またはコード ファイルの余白でねじ回し ![ねじ回しアイコン](../media/screwdriver-icon.png) アイコンをクリックします。

   ![LINQ から foreach への変換クイック アクション メニュー](media/convert-linq-to-foreach.png)

1. **['foreach' に変換]** を選択します。 または、 **[変更のプレビュー]** を選択して [[変更のプレビュー]](../../ide/preview-changes.md) ダイアログを開いて **[適用]** を選択します。

> [!NOTE]
> C# の場合、これらのリファクタリングによって生成されるコードでは、`foreach` ループのイテレーション変数には明示的な型または [var](/dotnet/csharp/language-reference/keywords/var) が使われます。 生成されるコードが明示的または暗黙的のどちらになるかは、スコープ内にのコード スタイルの設定によって決まります。 これらの特定のコード スタイルの設定は、コンピューター レベルの **[ツール]**  >  **[オプション]**  >  **[テキスト エディター]**  >  **[C#]**  >  **[コード スタイル]**  >  **[全般]**  >  **[\'var' を優先]** で、またはソリューション レベルの [EditorConfig](../../ide/editorconfig-language-conventions.md#implicit-and-explicit-types) ファイルで構成します。 コード スタイルの設定を **[オプション]** で変更した場合、変更を有効にするにはコード ファイルを開きなおします。

## <a name="see-also"></a>関連項目

- [LINQ](/dotnet/standard/using-linq)
- [リファクタリング](../refactoring-in-visual-studio.md)
- [変更のプレビュー](../../ide/preview-changes.md)