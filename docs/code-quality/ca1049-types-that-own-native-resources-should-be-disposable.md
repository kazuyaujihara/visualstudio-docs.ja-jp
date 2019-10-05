---
title: CA1049:ネイティブ リソースを所有する型は、破棄可能でなければなりません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1049
- TypesThatOwnNativeResourcesShouldBeDisposable
helpviewer_keywords:
- TypesThatOwnNativeResourcesShouldBeDisposable
- CA1049
ms.assetid: 084e587d-0e45-4092-b767-49eed30d6a35
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- cplusplus
ms.openlocfilehash: ef7b72eade7ea8e4486d5c317c06026bb4d0b95f
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235740"
---
# <a name="ca1049-types-that-own-native-resources-should-be-disposable"></a>CA1049:ネイティブ リソースを所有する型は、破棄可能でなければなりません

|||
|-|-|
|TypeName|TypesThatOwnNativeResourcesShouldBeDisposable|
|CheckId|CA1049|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

型が<xref:System.IntPtr?displayProperty=fullName>フィールド<xref:System.UIntPtr?displayProperty=fullName> 、フィールド、または<xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>フィールドを参照していますが、 <xref:System.IDisposable?displayProperty=fullName>を実装していません。

## <a name="rule-description"></a>規則の説明

この規則は、 <xref:System.IntPtr>、 <xref:System.UIntPtr>、 <xref:System.Runtime.InteropServices.HandleRef>の各フィールドがアンマネージリソースへのポインターを格納していることを前提としています。 アンマネージリソースを割り当てる型は<xref:System.IDisposable> 、を実装して、呼び出し元が必要に応じてリソースを解放し、リソースを保持するオブジェクトの有効期間を短縮できるようにする必要があります。

アンマネージリソースをクリーンアップするために推奨される設計パターンは、 <xref:System.Object.Finalize%2A?displayProperty=fullName>メソッド<xref:System.IDisposable.Dispose%2A?displayProperty=fullName>とメソッドを使用して、これらのリソースを解放するための暗黙的な方法と明示的な手段の両方を提供することです。 ガベージコレクターは、オブジェクト<xref:System.Object.Finalize%2A>が到達できなくなったと判断した後、一定の時間内にオブジェクトのメソッドを呼び出します。 が<xref:System.Object.Finalize%2A>呼び出された後、オブジェクトを解放するには、追加のガベージコレクションが必要です。 <xref:System.IDisposable.Dispose%2A>メソッドを使用すると、呼び出し元は、リソースがガベージコレクターに残されている場合に解放されるより前に、リソースを明示的に解放することができます。 アンマネージリソースをクリーンアップした後<xref:System.IDisposable.Dispose%2A> 、は<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>メソッドを呼び出して、呼び出しが不要に<xref:System.Object.Finalize%2A>なったことをガベージコレクターに知らせる必要があります。これにより、追加のガベージコレクションが不要になり、オブジェクトの有効期間。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、 <xref:System.IDisposable>を実装します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
型がアンマネージリソースを参照していない場合は、この規則からの警告を抑制することが安全です。 それ以外の場合は、実装<xref:System.IDisposable>に失敗すると、アンマネージリソースが使用できなくなったり、使用できなくなったりする可能性があるため、この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、アンマネージリソース<xref:System.IDisposable>をクリーンアップするためにを実装する型を示しています。

[!code-csharp[FxCop.Design.UnmanagedResources#1](../code-quality/codesnippet/CSharp/ca1049-types-that-own-native-resources-should-be-disposable_1.cs)]
[!code-vb[FxCop.Design.UnmanagedResources#1](../code-quality/codesnippet/VisualBasic/ca1049-types-that-own-native-resources-should-be-disposable_1.vb)]

## <a name="related-rules"></a>関連するルール
[CA2115GC を呼び出します。ネイティブリソースを使用する場合の KeepAlive](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)

[CA1816GC を呼び出します。Gc.suppressfinalize](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)

[CA2216破棄可能な型はファイナライザーを宣言しなければなりません](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

[CA1001: 破棄可能なフィールドを所有する型は、破棄可能でなければなりません](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)

## <a name="see-also"></a>関連項目

- [アンマネージ リソースのクリーンアップ](/dotnet/standard/garbage-collection/unmanaged)
- [Dispose パターン](/dotnet/standard/design-guidelines/dispose-pattern)