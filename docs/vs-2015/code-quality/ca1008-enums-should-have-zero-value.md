---
title: 'CA1008: 列挙型には0の値を指定する必要があります |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1008
- EnumsShouldHaveZeroValue
helpviewer_keywords:
- CA1008
- EnumsShouldHaveZeroValue
ms.assetid: 3503a73c-360c-416d-8ee4-c2aa44365a05
caps.latest.revision: 23
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: fbc7775d4ec41822b866868a6db6bceb353af989
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72668926"
---
# <a name="ca1008-enums-should-have-zero-value"></a>CA1008: Enums は 0 値を含んでいなければなりません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|EnumsShouldHaveZeroValue|
|CheckId|CA1008|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|非ブレーク-フラグ以外の列挙に**None**値を追加するように求めるメッセージが表示されます。中断-列挙値の名前変更または削除を求めるメッセージが表示された場合。|

## <a name="cause"></a>原因
 @No__t_0 が適用されていない列挙型では、値が0のメンバーは定義されません。または、適用されている <xref:System.FlagsAttribute> を持つ列挙体は、値が0でも名前が ' None ' でないメンバーを定義します。または、列挙体は複数の0値のメンバーを定義します。

## <a name="rule-description"></a>規則の説明
 初期化されていない列挙型の既定値は、他の値型と同様に、0です。 Flags 以外の属性が指定された列挙型では、値が0のメンバーを定義して、既定値が列挙型の有効な値になるようにする必要があります。 必要に応じて、メンバーに ' None ' という名前を指定します。 それ以外の場合は、最も頻繁に使用されるメンバーに0を割り当てます。 既定では、最初の列挙メンバーの値が宣言で設定されていない場合、その値は0になることに注意してください。

 @No__t_0 適用された列挙体に0値のメンバーが定義されている場合、列挙体に値が設定されていないことを示すには、その名前を ' None ' にする必要があります。 それ以外の目的で0値のメンバーを使用することは、<xref:System.FlagsAttribute> を使用するのとは対照的です。この場合、and 演算子と or 演算子は、メンバーでは使用できません。 これは、1つのメンバーに値0を割り当てる必要があることを意味します。 フラグ属性付き列挙で値0を持つ複数のメンバーが出現した場合、`Enum.ToString()` は0以外のメンバーに対して正しくない結果を返すことに注意してください。

## <a name="how-to-fix-violations"></a>違反の修正方法
 非フラグ-属性付き列挙に対するこの規則違反を修正するには、値が0のメンバーを定義します。これは、互換性に影響する変更点ではありません。 0値のメンバーを定義するフラグ属性付き列挙型の場合は、このメンバーに ' None ' という名前を付け、値が0の他のメンバーを削除します。これは、互換性に影響する変更点です。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 以前に出荷されたフラグ付きの列挙型の場合を除き、この規則からの警告を抑制しないでください。

## <a name="example"></a>例
 次の例は、規則を満たす2つの列挙体と、規則に違反する列挙型 `BadTraceOptions` を示しています。

 [!code-cpp[FxCop.Design.EnumsZeroValue#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumsZeroValue/cpp/FxCop.Design.EnumsZeroValue.cpp#1)]
 [!code-csharp[FxCop.Design.EnumsZeroValue#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumsZeroValue/cs/FxCop.Design.EnumsZeroValue.cs#1)]
 [!code-vb[FxCop.Design.EnumsZeroValue#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.EnumsZeroValue/vb/FxCop.Design.EnumsZeroValue.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA2217: enums を FlagsAttribute に設定しません](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

 [CA1700: enum 値に 'Reserved' という名前を指定しません](../code-quality/ca1700-do-not-name-enum-values-reserved.md)

 [CA1712: enum 値を型名のプレフィックスにしません](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

 [CA1028: 列挙ストレージは Int32 でなければなりません](../code-quality/ca1028-enum-storage-should-be-int32.md)

 [CA1027: FlagsAttribute で列挙値をマークします](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>参照
 <xref:System.Enum?displayProperty=fullName>
