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
ms.openlocfilehash: 81c9a94e318638837fb4ab8fe1a822dc0cfec46a
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57872757"
---
# <a name="ca2231-overload-operator-equals-on-overriding-valuetypeequals"></a>CA2231:ValueType.Equals のオーバーライドで、演算子 equals をオーバーロードします

|||
|-|-|
|TypeName|OverloadOperatorEqualsOnOverridingValueTypeEquals|
|CheckId|CA2231|
|Category|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

値型のオーバーライド<xref:System.Object.Equals%2A?displayProperty=fullName>しますが、等値演算子は実装されません。

既定では、このルールのみが検索に、外部から参照の種類が、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

ほとんどのプログラミング言語では、値型で等値演算子 (= =) の既定の実装はありません。 使用するプログラミング言語では、演算子のオーバー ロードをサポートする場合は、等値演算子の実装を検討してください。 その動作をする場合と同一の<xref:System.Object.Equals%2A>します。

オーバー ロードされた等値演算子の実装では、既定の等値演算子を使用できません。 こうと、スタック オーバーフローが発生します。 等値演算子を実装するには、実装で、Object.Equals メソッドを使用します。 例:

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

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告を抑制しても安全です。ただし、可能であれば、等値演算子を指定することをお勧めします。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca2231.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (使用) で構成できます。 詳細については、[構成 FxCop アナライザー](configure-fxcop-analyzers.md)を参照してください。

## <a name="example"></a>例

次の例では、この規則に違反する型を定義します。

[!code-csharp[FxCop.Usage.EqualsGetHashCode#1](../code-quality/codesnippet/CSharp/ca2231-overload-operator-equals-on-overriding-valuetype-equals_1.cs)]

## <a name="related-rules"></a>関連するルール

- [CA1046:参照型で、演算子 equals をオーバー ロードしません。](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)
- [CA2225:演算子のオーバー ロード名前付けされた代替](../code-quality/ca2225-operator-overloads-have-named-alternates.md)
- [CA2226:演算子は対称型オーバー ロードである必要があります。](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)
- [CA2224:オーバー ロードする演算子 equals で equals をオーバーライド](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2218:Equals をオーバーライドの GetHashCode をオーバーライドします。](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

## <a name="see-also"></a>関連項目

- <xref:System.Object.Equals%2A?displayProperty=fullName>