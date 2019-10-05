---
title: CA1804:使用されていないローカルを削除します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1804
- RemoveUnusedLocals
helpviewer_keywords:
- RemoveUnusedLocals
- CA1804
ms.assetid: cc332e67-6543-4813-bd8a-6f6fc75bf22a
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 0a83d0afffc50c7697fad98c4dc49e31770d63d4
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233746"
---
# <a name="ca1804-remove-unused-locals"></a>CA1804:使用されていないローカルを削除します

|||
|-|-|
|TypeName|RemoveUnusedLocals|
|CheckId|CA1804|
|カテゴリ|Microsoft.Performance|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
メソッドはローカル変数を宣言しますが、代入ステートメントの受信者としての場合を除き、変数は使用しません。 この規則による分析のために、テストされたアセンブリはデバッグ情報を使用してビルドする必要があり、関連付けられているプログラムデータベース (.pdb) ファイルが使用可能である必要があります。

## <a name="rule-description"></a>規則の説明
使用されていないローカル変数や不要な引数があると、アセンブリのサイズが大きくなり、パフォーマンスが低下します。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、ローカル変数を削除するか、使用します。

> [!NOTE]
> オプションが有効になっている場合C# 、コンパイラは使用されていないローカル変数を削除します。 `optimize`

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
変数がコンパイラによって生成された場合、このルールからの警告を非表示にします。 また、パフォーマンスとコードの保守が主要な問題でない場合は、このルールからの警告を抑制するか、ルールを無効にすることも安全です。

## <a name="example"></a>例
次の例では、使用されていないローカル変数をいくつか示します。

[!code-vb[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/VisualBasic/ca1804-remove-unused-locals_1.vb)]
[!code-csharp[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/CSharp/ca1804-remove-unused-locals_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA1809過度なローカルを避ける](../code-quality/ca1809-avoid-excessive-locals.md)

[CA1811呼び出されるプライベートコードを避ける](../code-quality/ca1811-avoid-uncalled-private-code.md)

[CA1812インスタンス内部クラスを回避する](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

[CA1801使用されていないパラメーターの確認](../code-quality/ca1801-review-unused-parameters.md)