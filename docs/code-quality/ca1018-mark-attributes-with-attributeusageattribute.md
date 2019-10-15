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
ms.openlocfilehash: 133ee073398817c037af95e2009c5acc98e1e5a2
ms.sourcegitcommit: 034c503ae04e22cf840ccb9770bffd012e40fb2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306135"
---
# <a name="ca1018-mark-attributes-with-attributeusageattribute"></a>CA1018:属性を AttributeUsageAttribute に設定します

|||
|-|-|
|TypeName|MarkAttributesWithAttributeUsage|
|CheckId|CA1018|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
@No__t-0 属性がカスタム属性に存在しません。

## <a name="rule-description"></a>規則の説明
カスタム属性を定義する場合は、<xref:System.AttributeUsageAttribute> を使用してマークします。これにより、ソースコード内でカスタム属性を適用できる場所が示されます。 属性の意味と用途によって、コード内の有効な位置が決まります。 たとえば、ライブラリ内の各型を管理および強化する担当者を識別する属性を定義し、その責任は常に型レベルで割り当てられます。 この場合、コンパイラはクラス、列挙、およびインターフェイスの属性を有効にする必要がありますが、メソッド、イベント、またはプロパティで有効にしないでください。 組織のポリシーと手順では、アセンブリで属性を有効にするかどうかを指定します。

@No__t-0 列挙体は、カスタム属性に対して指定できるターゲットを定義します。 @No__t-0 を省略した場合、<xref:System.AttributeTargets> 列挙の `All` の値で定義されているように、カスタム属性はすべてのターゲットに対して有効になります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、<xref:System.AttributeUsageAttribute> を使用して属性のターゲットを指定します。 次の例を参照してください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
メッセージを除外するのではなく、このルールの違反を修正する必要があります。 属性が <xref:System.AttributeUsageAttribute> を継承している場合でも、コードの保守を簡素化するために属性が存在している必要があります。

## <a name="example"></a>例
次の例では、2つの属性を定義します。 `BadCodeMaintainerAttribute` は <xref:System.AttributeUsageAttribute> ステートメントを誤って省略し、`GoodCodeMaintainerAttribute` は、このセクションで既に説明した属性を正しく実装します。 デザイン規則 [ CA1019 では、プロパティ `DeveloperName` が必要であることに注意してください。属性引数 @ no__t-0 に対してアクセサーを定義します。これは完全を期すために含まれています。

[!code-csharp[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/CSharp/ca1018-mark-attributes-with-attributeusageattribute_1.cs)]
[!code-vb[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/VisualBasic/ca1018-mark-attributes-with-attributeusageattribute_1.vb)]

## <a name="related-rules"></a>関連するルール
[CA1019:属性引数にアクセサーを定義する @ no__t-0

[CA1813:封印されていない属性を避ける @ no__t-0

## <a name="see-also"></a>関連項目

- [Attributes](/dotnet/standard/design-guidelines/attributes)