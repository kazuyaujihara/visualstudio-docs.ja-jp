---
title: CA2231:ValueType.Equals のオーバーライドで、演算子 equals をオーバーロードします
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
- OverrideOperatorEqualsOnOverridingValueTypeEquals
helpviewer_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
ms.assetid: 114c0161-261a-40ad-8b2c-0932d6909d2a
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: fafa4782762e18f1ced8c7f929720e995986ac7a
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69546869"
---
# <a name="ca2231-overload-operator-equals-on-overriding-valuetypeequals"></a>CA2231:ValueType.Equals のオーバーライドで、演算子 equals をオーバーロードします

|||
|-|-|
|TypeName|OverloadOperatorEqualsOnOverridingValueTypeEquals|
|CheckId|CA2231|
|Category|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

値型はを<xref:System.Object.Equals%2A?displayProperty=fullName>オーバーライドしますが、等値演算子を実装しません。

既定では、この規則は外部から参照できる型のみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

ほとんどのプログラミング言語では、値型に対して等値演算子 (= =) の既定の実装はありません。 プログラミング言語で演算子のオーバーロードがサポートされている場合は、等値演算子を実装することを検討してください。 その動作は、の<xref:System.Object.Equals%2A>動作と同じである必要があります。

等値演算子のオーバーロードされた実装では、既定の等値演算子を使用できません。 そうすると、スタックオーバーフローが発生します。 等値演算子を実装するには、実装で Object.equals メソッドを使用します。 例:

```vb
If (Object.ReferenceEquals(left, Nothing)) Then
    Return Object.ReferenceEquals(right, Nothing)
Else
    Return left.Equals(right)
End If
```

```csharp
if (Object.ReferenceEquals(left, null))
    return Object.ReferenceEquals(right, null);
return left.Equals(right);
```

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、等値演算子を実装します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

このルールからの警告を抑制するのは安全です。ただし、可能な限り等値演算子を指定することをお勧めします。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca2231.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (使用状況) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="example"></a>例

次の例では、この規則に違反する型を定義しています。

[!code-csharp[FxCop.Usage.EqualsGetHashCode#1](../code-quality/codesnippet/CSharp/ca2231-overload-operator-equals-on-overriding-valuetype-equals_1.cs)]

## <a name="related-rules"></a>関連するルール

- [CA1046参照型の演算子 equals をオーバーロードしない](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)
- [CA2225演算子のオーバーロードには代替の名前が付いています](../code-quality/ca2225-operator-overloads-have-named-alternates.md)
- [CA2226演算子には対称的なオーバーロードが必要です](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)
- [CA2224オーバーロードする演算子 equals で equals をオーバーライドします](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2218オーバーライドする Equals で GetHashCode をオーバーライドします](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

## <a name="see-also"></a>関連項目

- <xref:System.Object.Equals%2A?displayProperty=fullName>