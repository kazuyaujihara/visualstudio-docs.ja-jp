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
ms.openlocfilehash: 3ac52bdb17aeb7d04e434d2b02ff9a905eab49a2
ms.sourcegitcommit: 034c503ae04e22cf840ccb9770bffd012e40fb2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2019
ms.locfileid: "72305917"
---
# <a name="ca2216-disposable-types-should-declare-finalizer"></a>CA2216:破棄可能な型はファイナライザーを宣言しなければなりません

|||
|-|-|
|TypeName|DisposableTypesShouldDeclareFinalizer|
|CheckId|CA2216|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

@No__t 0 を実装し、アンマネージリソースの使用を提案するフィールドを持つ型は、<xref:System.Object.Finalize%2A?displayProperty=fullName> で説明されているように、ファイナライザーを実装しません。

## <a name="rule-description"></a>規則の説明

このルールの違反は、破棄可能な型に次の型のフィールドが含まれている場合に報告されます。

- <xref:System.IntPtr?displayProperty=fullName>

- <xref:System.UIntPtr?displayProperty=fullName>

- <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、@no__t 0 のメソッドを呼び出すファイナライザーを実装します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

アンマネージリソースを解放するために型が <xref:System.IDisposable> を実装していない場合は、この規則による警告を抑制するのが安全です。

## <a name="example"></a>例

次の例は、この規則に違反する型を示しています。

[!code-csharp[FxCop.Usage.DisposeNoFinalize#1](../code-quality/codesnippet/CSharp/ca2216-disposable-types-should-declare-finalizer_1.cs)]

## <a name="related-rules"></a>関連するルール

[CA2115:GC を呼び出します。ネイティブリソースを使用する場合の KeepAlive @ no__t

[CA1816:GC を呼び出します。Gc.suppressfinalize @ no__t-0

[CA1049:ネイティブリソースを所有する型は、破棄可能な @ no__t-0 である必要があります

## <a name="see-also"></a>関連項目

- <xref:System.IDisposable?displayProperty=fullName>
- <xref:System.IntPtr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>
- <xref:System.UIntPtr?displayProperty=fullName>
- <xref:System.Object.Finalize%2A?displayProperty=fullName>
- [Dispose パターン](/dotnet/standard/design-guidelines/dispose-pattern)