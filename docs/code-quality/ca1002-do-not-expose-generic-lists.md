---
title: CA1002:ジェネリック リストを公開しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotExposeGenericLists
- CA1002
helpviewer_keywords:
- CA1002
- DoNotExposeGenericLists
ms.assetid: 5caac810-1a79-47df-a27b-c46c5040bf34
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a6e300edf07aa98facbe6059ba9574e238ec8f3e
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923249"
---
# <a name="ca1002-do-not-expose-generic-lists"></a>CA1002:ジェネリック リストを公開しません

|||
|-|-|
|TypeName|DoNotExposeGenericLists|
|CheckId|CA1002|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
型に、外部から参照できる<xref:System.Collections.Generic.List%601?displayProperty=fullName>メンバーが含まれています。このメンバーは型である<xref:System.Collections.Generic.List%601?displayProperty=fullName>か、 <xref:System.Collections.Generic.List%601?displayProperty=fullName>型を返します。または、署名にパラメーターが含まれています。

## <a name="rule-description"></a>規則の説明
 <xref:System.Collections.Generic.List%601?displayProperty=fullName>は、パフォーマンスを目的として設計され、継承されないジェネリックコレクションです。 <xref:System.Collections.Generic.List%601?displayProperty=fullName>には、継承されたクラスの動作を簡単に変更できる仮想メンバーが含まれていません。 次のジェネリックコレクションは継承用に設計されているため<xref:System.Collections.Generic.List%601?displayProperty=fullName>、ではなく公開する必要があります。

- <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>

- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>

- <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、 <xref:System.Collections.Generic.List%601?displayProperty=fullName>型を継承用に設計されたジェネリックコレクションのいずれかに変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この警告を発生させるアセンブリが再利用可能なライブラリではない場合を除き、この規則からの警告を抑制しないでください。 たとえば、汎用リストを使用してパフォーマンスを向上させたパフォーマンスチューニングアプリケーションでは、この警告を抑制するのが安全です。

## <a name="related-rules"></a>関連するルール
[CA1005ジェネリック型のパラメーターが多すぎないようにする](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

[CA1010コレクションはジェネリックインターフェイスを実装する必要があります](../code-quality/ca1010-collections-should-implement-generic-interface.md)

[CA1000ジェネリック型の静的メンバーを宣言しません](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

[CA1006ジェネリック型をメンバーシグネチャに入れ子にしない](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

[CA1004ジェネリックメソッドは型パラメーターを指定しなければなりません](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

[CA1003汎用イベントハンドラーのインスタンスを使用する](../code-quality/ca1003-use-generic-event-handler-instances.md)

[CA1007適切な場所にジェネリックを使用する](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>関連項目
[ジェネリック](/dotnet/csharp/programming-guide/generics/index)