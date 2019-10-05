---
title: CA1815:equals および operator equals を値型でオーバーライドします
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1815
- OverrideEqualsAndOperatorEqualsOnValueTypes
helpviewer_keywords:
- OverrideEqualsAndOperatorEqualsOnValueTypes
- CA1815
ms.assetid: 0a8ab3a3-ee8e-46f7-985d-dcf00c89363b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 413119f7cdf473f3038ae212ac812d1987641bb1
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233547"
---
# <a name="ca1815-override-equals-and-operator-equals-on-value-types"></a>CA1815:equals および operator equals を値型でオーバーライドします

|||
|-|-|
|TypeName|OverrideEqualsAndOperatorEqualsOnValueTypes|
|CheckId|CA1815|
|カテゴリ|Microsoft.Performance|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

値型がオーバーライド<xref:System.Object.Equals%2A?displayProperty=fullName>されていないか、等値演算子 (= =) を実装していません。 このルールは列挙を確認しません。

既定では、この規則は外部から参照できる型のみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

値型の場合、の<xref:System.Object.Equals%2A>継承された実装はリフレクションライブラリを使用し、すべてのフィールドの内容を比較します。 Reflection は計算コストが高いため、場合によってはすべてのフィールドで等値性を比較する必要はありません。 ユーザーがインスタンスの比較または並べ替えを行うことが予想される場合、またはユーザーをハッシュテーブル<xref:System.Object.Equals%2A>キーとして使用する場合は、値の型を実装する必要があります。 お使いのプログラミング言語が演算子のオーバーロードに対応している場合、等値演算子と非等値演算子も実装してください。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、の<xref:System.Object.Equals%2A>実装を提供します。 可能な場合は、等値演算子を実装します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

値型のインスタンスが互いに比較されない場合は、この規則からの警告を抑制することが安全です。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca1815.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (パフォーマンス) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="example"></a>例

次のコードは、この規則に違反する構造体 (値型) を示しています。

[!code-csharp[FxCop.Performance.OverrideEqualsViolation#1](../code-quality/codesnippet/CSharp/ca1815-override-equals-and-operator-equals-on-value-types_1.cs)]

次のコードは、等値演算子 ( <xref:System.ValueType.Equals%2A?displayProperty=fullName> = =、! =) をオーバーライドして実装することによって、以前の違反を修正します。

[!code-csharp[FxCop.Performance.OverrideEqualsFixed#1](../code-quality/codesnippet/CSharp/ca1815-override-equals-and-operator-equals-on-value-types_2.cs)]

## <a name="related-rules"></a>関連するルール

- [CA2224オーバーロードする演算子 equals で equals をオーバーライドします](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2231: ValueType.Equals のオーバーライドで、演算子 equals をオーバーロードします](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)
- [CA2226演算子には対称的なオーバーロードが必要です](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

## <a name="see-also"></a>関連項目

- <xref:System.Object.Equals%2A?displayProperty=fullName>