---
title: CA1816:GC.SuppressFinalize を正しく呼び出します
ms.date: 06/30/2018
ms.topic: reference
f1_keywords:
- CA1816
- DisposeMethodsShouldCallSuppressFinalize
helpviewer_keywords:
- DisposeMethodsShouldCallSuppressFinalize
- CA1816
ms.assetid: 47915fbb-103f-4333-b157-1da16bf49660
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 3fdd20df37586e50b5236872f1d84de48d08c87a
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233524"
---
# <a name="ca1816-call-gcsuppressfinalize-correctly"></a>CA1816:GC.SuppressFinalize を正しく呼び出します

|||
|-|-|
|TypeName|CallGCSuppressFinalizeCorrectly|
|CheckId|CA1816|
|カテゴリ|エクスプローラー. 使用法|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

このルールの違反の原因として、次のことが考えられます。

- の<xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>実装であり、を呼び出さ<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>ないメソッド。

- の<xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>実装ではなく、を呼び出す<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>メソッド。

- を呼び出し<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> 、 [thisC#()](/dotnet/csharp/language-reference/keywords/this)または[Me (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass#me)以外の何かを渡すメソッド。

## <a name="rule-description"></a>規則の説明

メソッド<xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>は、オブジェクトがガベージコレクションに使用できるようになる前に、いつでもユーザーがリソースを解放できるようにします。 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>メソッドが呼び出されると、オブジェクトのリソースが解放されます。 これにより、終了処理は不要になります。 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>ガベージコレクター <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>がオブジェクトのファイナライザーを呼び出さないように、を呼び出す必要があります。

ファイナライザーを使用した派生型を再実装<xref:System.IDisposable>したり呼び出したりする必要がないようにするに<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>は、ファイナライザーのないシールされた型は引き続きを呼び出す必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、次のようにします。

- メソッドがの実装である場合<xref:System.IDisposable.Dispose%2A>は、へ<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>の呼び出しを追加します。

- メソッドがの実装でない場合は<xref:System.IDisposable.Dispose%2A>、の呼び出しを削除する<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>か、型の<xref:System.IDisposable.Dispose%2A>実装に移動します。

- に対するすべての<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>呼び出しを変更して、 [thisC#()](/dotnet/csharp/language-reference/keywords/this)または[Me (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass#me)を渡します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

を意図的に使用して他のオブジェクトの有効期間<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>を制御している場合にのみ、この規則の警告を非表示にします。 の<xref:System.IDisposable.Dispose%2A>実装でが呼び出さ<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>れない場合は、この規則による警告を抑制しないでください。 この場合、終了処理を抑制しないとパフォーマンスが低下し、利点はありません。

## <a name="example-that-violates-ca1816"></a>CA1816 に違反する例

このコードは、を呼び出す<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>メソッドを示していますが、このメソッド[(C#)](/dotnet/csharp/language-reference/keywords/this)または[Me (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass#me)を渡しません。 このため、このコードは rule CA1816 に違反します。

[!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../code-quality/codesnippet/VisualBasic/ca1816-call-gc-suppressfinalize-correctly_1.vb)]
[!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../code-quality/codesnippet/CSharp/ca1816-call-gc-suppressfinalize-correctly_1.cs)]

## <a name="example-that-satisfies-ca1816"></a>CA1816 を満たす例

この例は、[この (C#)](/dotnet/csharp/language-reference/keywords/this)また<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>は[Me (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass#me)を渡すことによって、を正しく呼び出すメソッドを示しています。

[!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../code-quality/codesnippet/VisualBasic/ca1816-call-gc-suppressfinalize-correctly_2.vb)]
[!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../code-quality/codesnippet/CSharp/ca1816-call-gc-suppressfinalize-correctly_2.cs)]

## <a name="related-rules"></a>関連するルール

- [CA2215Dispose メソッドは基底クラスの dispose を呼び出す必要があります](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)
- [CA2216破棄可能な型はファイナライザーを宣言しなければなりません](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

## <a name="see-also"></a>関連項目

- [Dispose パターン](/dotnet/standard/design-guidelines/dispose-pattern)