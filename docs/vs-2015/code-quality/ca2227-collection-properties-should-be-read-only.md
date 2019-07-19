---
title: CA2227:コレクションのプロパティは読み取り専用にする |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
helpviewer_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
ms.assetid: 26967aaf-6fbe-438a-b4d3-ac579b5dc0f9
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 3182a254ed5e22c560523911f87dc852708a9eb1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201593"
---
# <a name="ca2227-collection-properties-should-be-read-only"></a>CA2227:Collection プロパティは読み取り専用でなければなりません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|CollectionPropertiesShouldBeReadOnly|
|CheckId|CA2227|
|Category|Microsoft.Usage|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 外部から見えるの書き込み可能なプロパティが実装する型<xref:System.Collections.ICollection?displayProperty=fullName>します。 ルールでは、配列、インデクサー ('Item' という名前のプロパティ)、およびアクセス許可セットは無視されます。

## <a name="rule-description"></a>規則の説明
 書き込み可能なコレクション プロパティには、完全に別のコレクションで置換するユーザーができます。 読み取り専用プロパティは、コレクションを置換できないようにしますが、個別のメンバーが設定されることは回避できません。 コレクションの置換が目標の場合、推奨される設計パターンが、コレクションからすべての要素を削除するメソッドをおよびコレクションを再設定するメソッドが含まれます。 参照してください、<xref:System.Collections.ArrayList.Clear%2A>と<xref:System.Collections.ArrayList.AddRange%2A>のメソッド、<xref:System.Collections.ArrayList?displayProperty=fullName>このパターンの例のクラス。

 バイナリおよび XML シリアル化の両方は、コレクションである読み取り専用のプロパティをサポートします。 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>クラスに実装する型の特定の要件は<xref:System.Collections.ICollection>と<xref:System.Collections.IEnumerable?displayProperty=fullName>シリアル化可能にするためにします。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、読み取り専用プロパティを作成し、設計上必要な場合をオフにし、コレクションを再作成するメソッドを追加します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例では、書き込み可能なコレクションのプロパティを持つ型を表示し、コレクションを直接置換する方法を示しています。 推奨される方法を使用して読み取り専用のコレクション プロパティに置き換えるさらに、`Clear`と`AddRange`メソッドが表示されます。

 [!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.PropertiesReturningCollections/cpp/FxCop.Usage.PropertiesReturningCollections.cpp#1)]
 [!code-csharp[FxCop.Usage.PropertiesReturningCollections#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.PropertiesReturningCollections/cs/FxCop.Usage.PropertiesReturningCollections.cs#1)]
 [!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.PropertiesReturningCollections/vb/FxCop.Usage.PropertiesReturningCollections.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA 1819:プロパティは、配列を返す必要がありますいません。](../code-quality/ca1819-properties-should-not-return-arrays.md)
