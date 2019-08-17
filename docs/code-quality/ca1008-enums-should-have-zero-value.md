---
title: CA1008:Enums は 0 値を含んでいなければなりません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1008
- EnumsShouldHaveZeroValue
helpviewer_keywords:
- CA1008
- EnumsShouldHaveZeroValue
ms.assetid: 3503a73c-360c-416d-8ee4-c2aa44365a05
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 502033d2adffd640d2af6ee8d36b0c0f3cd71472
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547938"
---
# <a name="ca1008-enums-should-have-zero-value"></a>CA1008:Enums は 0 値を含んでいなければなりません

|||
|-|-|
|TypeName|EnumsShouldHaveZeroValue|
|CheckId|CA1008|
|Category|Microsoft.Design|
|互換性に影響する変更点|非ブレーク-フラグ以外の列挙に**None**値を追加するように求めるメッセージが表示されます。 中断-列挙値の名前変更または削除を求めるメッセージが表示された場合。|

## <a name="cause"></a>原因

が適用さ<xref:System.FlagsAttribute?displayProperty=fullName>れていない列挙型では、値が0のメンバーは定義されません。 または、が適用され<xref:System.FlagsAttribute>ている列挙体は、値が0で、名前が ' None ' ではないメンバーを定義します。 または、列挙体は、ゼロ値の複数のメンバーを定義します。

既定では、この規則は外部から参照できる列挙のみを参照しますが、これは[構成可能](#configurability)です。

## <a name="rule-description"></a>規則の説明

初期化されていない列挙型の既定値は、他の値型と同様に、0です。 フラグ属性以外の列挙体では、値が0のメンバーを定義して、既定値が列挙型の有効な値になるようにする必要があります。 必要に応じて、メンバーに ' None ' という名前を指定します。 それ以外の場合は、最も頻繁に使用されるメンバーに0を割り当てます。 既定では、最初の列挙メンバーの値が宣言で設定されていない場合、その値は0になります。

<xref:System.FlagsAttribute>適用されたを持つ列挙体に0値のメンバーが定義されている場合、その名前は、列挙体に値が設定されていないことを示す "None" にする必要があります。 それ以外の目的で0値のメンバーを使用することは、と、 <xref:System.FlagsAttribute>またはのビットごとの演算子がメンバーで使用できないという意味で、を使用することとは対照的です。 これは、1つのメンバーに値0を割り当てる必要があることを意味します。 値0を持つ複数のメンバーがフラグ属性付きの列挙体で発生`Enum.ToString()`した場合、は0以外のメンバーに対して正しくない結果を返します。

## <a name="how-to-fix-violations"></a>違反の修正方法

非フラグ属性付き列挙型のこの規則違反を修正するには、値0を持つメンバーを定義します。これは、互換性に影響する変更点ではありません。 0値のメンバーを定義するフラグ属性付き列挙型の場合は、このメンバーに ' None ' という名前を付け、値が0の他のメンバーを削除します。これは、互換性に影響する変更点です。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

以前に出荷されたフラグ付きの列挙型の場合を除き、この規則からの警告を抑制しないでください。

## <a name="configurability"></a>かつ

この規則を[FxCop アナライザー](install-fxcop-analyzers.md) (レガシ分析ではなく) から実行している場合は、ユーザー補助に基づいて、この規則を実行するコードベースの部分を構成できます。 たとえば、パブリックでない API サーフェイスに対してのみルールを実行するように指定するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.ca1008.api_surface = private, internal
```

このオプションは、この規則、すべての規則、またはこのカテゴリのすべての規則 (デザイン) に対してのみ構成できます。 詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="example"></a>例

次の例では、規則に適合する2つの列挙`BadTraceOptions`体と、規則に違反する列挙体を示します。

[!code-cpp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CPP/ca1008-enums-should-have-zero-value_1.cpp)]
[!code-csharp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CSharp/ca1008-enums-should-have-zero-value_1.cs)]
[!code-vb[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/VisualBasic/ca1008-enums-should-have-zero-value_1.vb)]

## <a name="related-rules"></a>関連するルール

- [CA2217FlagsAttribute で列挙をマークしない](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)
- [CA1700列挙値に ' Reserved ' という名前を指定することはできません](../code-quality/ca1700-do-not-name-enum-values-reserved.md)
- [CA1712列挙値の型名をプレフィックスとして使用しない](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)
- [CA1028列挙ストレージは Int32 でなければなりません](../code-quality/ca1028-enum-storage-should-be-int32.md)
- [CA1027FlagsAttribute で列挙をマークする](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>関連項目

- <xref:System.Enum?displayProperty=fullName>