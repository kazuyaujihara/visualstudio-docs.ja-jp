---
title: 'CA1049: ネイティブ リソースを所有する型は、破棄可能でなければなりません'
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
ms.openlocfilehash: a39d1e03da062f3030571820e98898d5122d495f
ms.sourcegitcommit: 1507baf3a336bbb6511d4c3ce73653674831501b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72349099"
---
# <a name="ca1049-types-that-own-native-resources-should-be-disposable"></a>CA1049: ネイティブ リソースを所有する型は、破棄可能でなければなりません

|||
|-|-|
|TypeName|TypesThatOwnNativeResourcesShouldBeDisposable|
|CheckId|CA1049|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

型は @no__t 0 フィールド、@no__t 1 フィールド、または <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName> フィールドを参照しますが、<xref:System.IDisposable?displayProperty=fullName> を実装していません。

## <a name="rule-description"></a>規則の説明

このルールでは、<xref:System.IntPtr>、<xref:System.UIntPtr>、および <xref:System.Runtime.InteropServices.HandleRef> の各フィールドにアンマネージリソースへのポインターが格納されていることを前提としています。 アンマネージリソースを割り当てる型は @no__t 0 を実装して、呼び出し元が必要に応じてリソースを解放し、リソースを保持するオブジェクトの有効期間を短縮できるようにする必要があります。

アンマネージリソースをクリーンアップするために推奨される設計パターンは、<xref:System.Object.Finalize%2A?displayProperty=fullName> メソッドと <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> メソッドをそれぞれ使用して、これらのリソースを解放するための暗黙的な方法と明示的な手段の両方を提供することです。 ガベージコレクターは、オブジェクトが到達できなくなったと判断した後で、オブジェクトの <xref:System.Object.Finalize%2A> メソッドを呼び出します。 @No__t-0 が呼び出されると、オブジェクトを解放するために追加のガベージコレクションが必要になります。 @No__t-0 メソッドを使用すると、リソースがガベージコレクターに残されている場合は解放される前に、呼び出し元はリソースを明示的に解放できます。 アンマネージリソースをクリーンアップした後、<xref:System.IDisposable.Dispose%2A> は <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> メソッドを呼び出す必要があります。これにより、@no__t 2 が呼び出されなくなることをガベージコレクターに知らせることができます。これにより、追加のガベージコレクションが不要になり、オブジェクトの有効期間が短縮されます。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、<xref:System.IDisposable> を実装します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
型がアンマネージリソースを参照していない場合は、この規則からの警告を抑制することが安全です。 それ以外の場合は、<xref:System.IDisposable> の実装に失敗すると、アンマネージリソースが使用できなくなったり、使用されなくなったりする可能性があるため、この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、アンマネージリソースをクリーンアップするために <xref:System.IDisposable> を実装する型を示しています。

[!code-csharp[FxCop.Design.UnmanagedResources#1](../code-quality/codesnippet/CSharp/ca1049-types-that-own-native-resources-should-be-disposable_1.cs)]
[!code-vb[FxCop.Design.UnmanagedResources#1](../code-quality/codesnippet/VisualBasic/ca1049-types-that-own-native-resources-should-be-disposable_1.vb)]

## <a name="related-rules"></a>関連するルール
[CA2115: ネイティブ リソースを使用しているときには GC.KeepAlive を呼び出します](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)

[CA1816: GC.SuppressFinalize を正しく呼び出します](../code-quality/ca1816.md)

[CA2216: 破棄できる型ではファイナライザーを宣言します](../code-quality/ca2216.md)

[CA1001: 破棄可能なフィールドを所有する型は、破棄可能でなければなりません](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)

## <a name="see-also"></a>関連項目

- [アンマネージ リソースのクリーンアップ](/dotnet/standard/garbage-collection/unmanaged)
- [Dispose パターン](/dotnet/standard/design-guidelines/dispose-pattern)