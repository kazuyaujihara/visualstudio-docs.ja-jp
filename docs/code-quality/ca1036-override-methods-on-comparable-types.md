---
title: CA1036:比較可能な型でメソッドをオーバーライドします
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1036
- OverrideMethodsOnComparableTypes
helpviewer_keywords:
- OverrideMethodsOnComparableTypes
- CA1036
ms.assetid: 2329f844-4cb8-426d-bee2-cd065d1346d0
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: be340314afe36f3a930474f345715965f566b2d4
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236002"
---
# <a name="ca1036-override-methods-on-comparable-types"></a>CA1036:比較可能な型でメソッドをオーバーライドします

|||
|-|-|
|TypeName|OverrideMethodsOnComparableTypes|
|CheckId|CA1036|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

型が<xref:System.IComparable?displayProperty=fullName>インターフェイスを実装していて<xref:System.Object.Equals%2A?displayProperty=fullName> 、がオーバーライドされていないか、または言語固有の演算子の等値、非等値、小なり、またはより大きい値をオーバーロードしていません。 型がインターフェイスの実装のみを継承する場合、規則は違反を報告しません。

既定では、この規則はパブリックおよび保護された型のみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

カスタム並べ替え順序を定義する型は、 <xref:System.IComparable>インターフェイスを実装します。 メソッド<xref:System.IComparable.CompareTo%2A>は、型の2つのインスタンスの正しい並べ替え順序を示す整数値を返します。 このルールは、並べ替え順序を設定する型を識別します。 並べ替え順序を設定することは、通常、等値、非等値、小なり値、およびそれ以上が適用されないことを意味します。 の<xref:System.IComparable>実装を提供する場合は、通常、と<xref:System.IComparable.CompareTo%2A>一致<xref:System.Object.Equals%2A>する値を返すようにをオーバーライドする必要もあります。 をオーバーライド<xref:System.Object.Equals%2A>し、演算子のオーバーロードをサポートする言語でコーディングする場合は、と<xref:System.Object.Equals%2A>一致する演算子も指定する必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、 <xref:System.Object.Equals%2A>をオーバーライドします。 プログラミング言語で演算子のオーバーロードがサポートされている場合は、次の演算子を指定します。

- op_Equality
- op_Inequality
- op_LessThan
- op_GreaterThan

でC#は、これらの演算子を表すために使用されるトークンは次のとおりです。

```csharp
==
!=
<
>
```

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

CA1036 の Visual Basic 場合と同様に、違反の原因が演算子の不足によるものであり、プログラミング言語で演算子のオーバーロードがサポートされていない場合は、ルールからの警告を抑制するのが安全です。 演算子の実装がアプリのコンテキストで意味を持たないと判断した場合は、op_Equality 以外の等値演算子でこの規則が発生したときに、警告を抑制することも安全です。 ただし、をオーバーライド<xref:System.Object.Equals%2A?displayProperty=nameWithType>する場合は、常に op_Equality と = = 演算子をオーバーライドする必要があります。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca1036.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (デザイン) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="examples"></a>使用例

次のコードには、を正しく実装<xref:System.IComparable>する型が含まれています。 コードコメントは、 <xref:System.Object.Equals%2A> <xref:System.IComparable>およびインターフェイスに関連するさまざまな規則を満たすメソッドを識別します。

[!code-csharp[FxCop.Design.IComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_1.cs)]

次のアプリケーションコードは、前に示し<xref:System.IComparable>た実装の動作をテストします。

[!code-csharp[FxCop.Design.TestIComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_2.cs)]

## <a name="see-also"></a>関連項目

- <xref:System.IComparable?displayProperty=fullName>
- <xref:System.Object.Equals%2A?displayProperty=fullName>
- [等値演算子](/dotnet/standard/design-guidelines/equality-operators)