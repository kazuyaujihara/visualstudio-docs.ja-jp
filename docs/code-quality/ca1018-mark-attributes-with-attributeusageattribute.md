---
title: CA1018:属性を AttributeUsageAttribute に設定します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
helpviewer_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
ms.assetid: 6ab70ec0-220f-4880-af31-45067703133c
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 78917bcd4c67e1da205595bac07c8e0e5947318d
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923059"
---
# <a name="ca1018-mark-attributes-with-attributeusageattribute"></a>CA1018:属性を AttributeUsageAttribute に設定します

|||
|-|-|
|TypeName|MarkAttributesWithAttributeUsage|
|CheckId|CA1018|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
この<xref:System.AttributeUsageAttribute?displayProperty=fullName>属性はカスタム属性に存在しません。

## <a name="rule-description"></a>規則の説明
カスタム属性を定義するときは、を使用<xref:System.AttributeUsageAttribute>して、カスタム属性を適用できるソースコード内の場所を指定します。 属性の意味と用途によって、コード内の有効な位置が決まります。 たとえば、ライブラリ内の各型を管理および強化する担当者を識別する属性を定義し、その責任は常に型レベルで割り当てられます。 この場合、コンパイラはクラス、列挙、およびインターフェイスの属性を有効にする必要がありますが、メソッド、イベント、またはプロパティで有効にしないでください。 組織のポリシーと手順では、アセンブリで属性を有効にするかどうかを指定します。

列挙<xref:System.AttributeTargets?displayProperty=fullName>体は、カスタム属性に対して指定できるターゲットを定義します。 を省略<xref:System.AttributeUsageAttribute>した場合、カスタム属性は、列挙体の`All` <xref:System.AttributeTargets>値で定義されているすべてのターゲットに対して有効になります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、を使用<xref:System.AttributeUsageAttribute>して、属性のターゲットを指定します。 次の例を参照してください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
メッセージを除外するのではなく、このルールの違反を修正する必要があります。 属性が継承<xref:System.AttributeUsageAttribute>されている場合でも、コードの保守を簡素化するために属性が存在している必要があります。

## <a name="example"></a>例
次の例では、2つの属性を定義します。 `BadCodeMaintainerAttribute`<xref:System.AttributeUsageAttribute>ステートメントを誤って省略し`GoodCodeMaintainerAttribute` 、このセクションの前半で説明した属性を正しく実装します。 デザインルール`DeveloperName` [CA1019 では、プロパティが必要であることに注意してください。属性引数](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)にアクセサーを定義し、完全を期すために含めます。

[!code-csharp[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/CSharp/ca1018-mark-attributes-with-attributeusageattribute_1.cs)]
[!code-vb[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/VisualBasic/ca1018-mark-attributes-with-attributeusageattribute_1.vb)]

## <a name="related-rules"></a>関連するルール
[CA1019属性引数にアクセサーを定義する](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)

[CA1813:封印されていない属性を避ける](../code-quality/ca1813-avoid-unsealed-attributes.md)

## <a name="see-also"></a>関連項目

- [属性](/dotnet/standard/design-guidelines/attributes)