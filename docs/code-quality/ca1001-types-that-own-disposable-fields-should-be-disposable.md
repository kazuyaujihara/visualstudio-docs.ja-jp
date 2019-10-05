---
title: CA1001:破棄可能なフィールドを所有する型は、破棄可能でなければなりません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
helpviewer_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
ms.assetid: c85c126c-2b16-4505-940a-b5ddf873fb22
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 3bda8fc80992a2246c30e28582eb93b4624ab81c
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236690"
---
# <a name="ca1001-types-that-own-disposable-fields-should-be-disposable"></a>CA1001:破棄可能なフィールドを所有する型は、破棄可能でなければなりません

|||
|-|-|
|TypeName|TypesThatOwnDisposableFieldsShouldBeDisposable|
|CheckId|CA1001|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|非互換性-型がアセンブリの外部で参照できない場合。<br /><br /> 中断-型がアセンブリの外部で参照可能な場合。|

## <a name="cause"></a>原因
クラスは、 <xref:System.IDisposable?displayProperty=fullName>型のインスタンスフィールドを宣言して実装します。クラスはを<xref:System.IDisposable>実装しません。

## <a name="rule-description"></a>規則の説明
クラスは、所有<xref:System.IDisposable>しているアンマネージリソースを破棄するためのインターフェイスを実装します。 <xref:System.IDisposable>型のインスタンスフィールドは、そのフィールドがアンマネージリソースを所有していることを示します。 <xref:System.IDisposable>フィールドを宣言するクラスは、間接的にアンマネージリソースを所有<xref:System.IDisposable>し、インターフェイスを実装する必要があります。 クラスがアンマネージリソースを直接所有していない場合は、ファイナライザーを実装しないでください。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、 <xref:System.IDisposable> <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>メソッドからを実装し、 <xref:System.IDisposable.Dispose%2A>フィールドのメソッドを呼び出します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、規則に違反するクラスと、を実装<xref:System.IDisposable>することによって規則を満たすクラスを示しています。 クラスがアンマネージリソースを直接所有していないため、クラスはファイナライザーを実装しません。

[!code-vb[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/VisualBasic/ca1001-types-that-own-disposable-fields-should-be-disposable_1.vb)]
[!code-csharp[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/CSharp/ca1001-types-that-own-disposable-fields-should-be-disposable_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA2213: 破棄可能なフィールドは破棄されなければなりません](../code-quality/ca2213-disposable-fields-should-be-disposed.md)

[CA2216破棄可能な型はファイナライザーを宣言しなければなりません](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

[CA2215Dispose メソッドは基底クラスの dispose を呼び出す必要があります](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)

[CA1049ネイティブリソースを所有する型は、破棄可能である必要があります](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)