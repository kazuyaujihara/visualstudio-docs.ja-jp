---
title: 'CA1027: FlagsAttribute | で列挙をマークします。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkEnumsWithFlags
- CA1027
helpviewer_keywords:
- CA1027
- MarkEnumsWithFlags
ms.assetid: 249e882c-8cd1-4c00-a2de-7b6bdc1849ff
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 6f2dc7dcd79fbcaf47a2db3cf49f22f3467a06ab
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661930"
---
# <a name="ca1027-mark-enums-with-flagsattribute"></a>CA1027: FlagsAttribute で列挙値をマークします
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MarkEnumsWithFlags|
|CheckId|CA1027|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 パブリック列挙型の値は、列挙体で定義されている2つの値またはその他の値の組み合わせであり、<xref:System.FlagsAttribute?displayProperty=fullName> 属性は存在しません。 誤検知を減らすために、このルールは連続した値を持つ列挙に対する違反を報告しません。

## <a name="rule-description"></a>規則の説明
 列挙型は、関連する名前付き定数が複数定義された値型です。 名前付き定数を明確に結合できる場合は、列挙体に <xref:System.FlagsAttribute> を適用します。 たとえば、アプリケーションの曜日を列挙して、使用可能なリソースを追跡する場合を考えてみます。 各リソースの可用性が <xref:System.FlagsAttribute> 存在する列挙体を使用してエンコードされている場合は、日付の任意の組み合わせを表すことができます。 属性を指定しない場合は、1週間の曜日のみを表すことができます。

 組み合わせ可能な列挙体を格納するフィールドの場合、個々の列挙値はフィールド内のビットのグループとして扱われます。 そのため、このようなフィールドは、*ビットフィールド*と呼ばれることもあります。 ビットフィールドに格納する列挙値を結合するには、ブール条件演算子を使用します。 ビットフィールドをテストして特定の列挙値が存在するかどうかを判断するには、ブール型の論理演算子を使用します。 ビットフィールドで結合された列挙値を正しく格納および取得するには、列挙体に定義されている各値が2の累乗である必要があります。 そうでない限り、ブール型の論理演算子は、フィールドに格納されている個々の列挙値を抽出できません。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、列挙体に <xref:System.FlagsAttribute> を追加します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 列挙値を組み合わせ可能にしない場合は、この規則からの警告を非表示にします。

## <a name="example"></a>例
 次の例では、`DaysEnumNeedsFlags` は <xref:System.FlagsAttribute> を使用するための要件を満たしていますが、それが含まれていない列挙体です。 @No__t_0 列挙体には2の累乗の値はありませんが、<xref:System.FlagsAttribute> は正しく指定されていません。 これは rule [CA2217 に違反します: FlagsAttribute で列挙をマークしません](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)。

 [!code-csharp[FxCop.Design.EnumFlags#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumFlags/cs/FxCop.Design.EnumFlags.cs#1)]

## <a name="related-rules"></a>関連規則
 [CA2217: enums を FlagsAttribute に設定しません](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>参照
 <xref:System.FlagsAttribute?displayProperty=fullName>
