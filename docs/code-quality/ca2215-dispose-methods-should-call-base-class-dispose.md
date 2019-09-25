---
title: CA2215:Dispose メソッドが基底クラスの Dispose を呼び出す必要があります
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2215
- DisposeMethodsShouldCallBaseClassDispose
- Dispose methods should call base class dispose
helpviewer_keywords:
- DisposeMethodsShouldCallBaseClassDispose
- CA2215
ms.assetid: c772e7a6-a87e-425c-a70e-912664ae9042
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 468b63ca554ea126bbd621a2502e54540e6ed068
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231281"
---
# <a name="ca2215-dispose-methods-should-call-base-class-dispose"></a>CA2215:Dispose メソッドが基底クラスの Dispose を呼び出す必要があります

|||
|-|-|
|TypeName|DisposeMethodsShouldCallBaseClassDispose|
|CheckId|CA2215|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
を実装する<xref:System.IDisposable?displayProperty=fullName>型は、も実装<xref:System.IDisposable>する型から継承します。 継承する型の<xref:System.IDisposable.Dispose%2A> メソッドは、親の型のメソッドを呼び出しません。<xref:System.IDisposable.Dispose%2A>

## <a name="rule-description"></a>規則の説明
型が破棄可能な型から継承する場合は、独自<xref:System.IDisposable.Dispose%2A> <xref:System.IDisposable.Dispose%2A>のメソッド内から基本型のメソッドを呼び出す必要があります。 基本型のメソッド Dispose を呼び出すと、基本型によって作成されたすべてのリソースが解放されます。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、 `base`を呼び出します。<xref:System.IDisposable.Dispose%2A> <xref:System.IDisposable.Dispose%2A>メソッド内。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
を`base`呼び出した場合、このルールからの警告を抑制するのは安全です。<xref:System.IDisposable.Dispose%2A> ルールチェックよりも深い呼び出しレベルで発生します。

## <a name="example"></a>例
を実装`TypeA` <xref:System.IDisposable>する型の例を次に示します。

[!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2215-dispose-methods-should-call-base-class-dispose_1.cs)]

## <a name="example"></a>例
次の例は、型`TypeB` `TypeA`を継承し、その<xref:System.IDisposable.Dispose%2A>メソッドを正しく呼び出す型を示しています。

[!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2215-dispose-methods-should-call-base-class-dispose_2.vb)]

## <a name="see-also"></a>関連項目

- <xref:System.IDisposable?displayProperty=fullName>
- [Dispose パターン](/dotnet/standard/design-guidelines/dispose-pattern)