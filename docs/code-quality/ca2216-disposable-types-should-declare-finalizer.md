---
title: CA2216:破棄可能な型はファイナライザーを宣言しなければなりません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DisposableTypesShouldDeclareFinalizer
- CA2216
helpviewer_keywords:
- CA2216
- DisposableTypesShouldDeclareFinalizer
ms.assetid: 0cabcc5e-b526-452b-8c2a-0cbe3b93c0ef
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1616e889b3892aa656692a3e5b0895d4b131b7f1
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231251"
---
# <a name="ca2216-disposable-types-should-declare-finalizer"></a>CA2216:破棄可能な型はファイナライザーを宣言しなければなりません

|||
|-|-|
|TypeName|DisposableTypesShouldDeclareFinalizer|
|CheckId|CA2216|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

を実装<xref:System.IDisposable?displayProperty=fullName>し、アンマネージリソースの使用を提案するフィールドを持つ型は、「」で<xref:System.Object.Finalize%2A?displayProperty=fullName>説明されているように、ファイナライザーを実装しません。

## <a name="rule-description"></a>規則の説明

このルールの違反は、破棄可能な型に次の型のフィールドが含まれている場合に報告されます。

- <xref:System.IntPtr?displayProperty=fullName>

- <xref:System.UIntPtr?displayProperty=fullName>

- <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、 <xref:System.IDisposable.Dispose%2A>メソッドを呼び出すファイナライザーを実装します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

アンマネージリソースを解放するために型がを実装<xref:System.IDisposable>していない場合は、この規則による警告を抑制することが安全です。

## <a name="example"></a>例

次の例は、この規則に違反する型を示しています。

[!code-csharp[FxCop.Usage.DisposeNoFinalize#1](../code-quality/codesnippet/CSharp/ca2216-disposable-types-should-declare-finalizer_1.cs)]

## <a name="related-rules"></a>関連するルール

[CA2115GC を呼び出します。ネイティブリソースを使用する場合の KeepAlive](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)

[CA1816GC を呼び出します。Gc.suppressfinalize](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)

[CA1049ネイティブリソースを所有する型は、破棄可能である必要があります](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)

## <a name="see-also"></a>関連項目

- <xref:System.IDisposable?displayProperty=fullName>
- <xref:System.IntPtr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>
- <xref:System.UIntPtr?displayProperty=fullName>
- <xref:System.Object.Finalize%2A?displayProperty=fullName>
- [Dispose パターン](/dotnet/standard/design-guidelines/dispose-pattern)