---
title: 'CA1049: ネイティブリソースを所有する型は、破棄可能である必要があります |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1049
- TypesThatOwnNativeResourcesShouldBeDisposable
helpviewer_keywords:
- TypesThatOwnNativeResourcesShouldBeDisposable
- CA1049
ms.assetid: 084e587d-0e45-4092-b767-49eed30d6a35
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: aaaf95346c51e2cb5cadb01a39e482bb508bc764
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72668905"
---
# <a name="ca1049-types-that-own-native-resources-should-be-disposable"></a>CA1049: ネイティブ リソースを所有する型は、破棄可能でなければなりません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TypesThatOwnNativeResourcesShouldBeDisposable|
|CheckId|CA1049|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 型は、<xref:System.IntPtr?displayProperty=fullName> フィールド、<xref:System.UIntPtr?displayProperty=fullName> フィールド、または <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName> フィールドを参照していますが、<xref:System.IDisposable?displayProperty=fullName> を実装していません。

## <a name="rule-description"></a>規則の説明
 このルールでは、<xref:System.IntPtr>、<xref:System.UIntPtr>、および <xref:System.Runtime.InteropServices.HandleRef> の各フィールドにアンマネージリソースへのポインターが格納されていることを前提としています。 アンマネージリソースを割り当てる型は、<xref:System.IDisposable> を実装して、呼び出し元が必要に応じてリソースを解放し、リソースを保持するオブジェクトの有効期間を短縮できるようにする必要があります。

 アンマネージリソースをクリーンアップするために推奨されるデザインパターンは、それぞれ <xref:System.Object.Finalize%2A?displayProperty=fullName> メソッドと <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> メソッドを使用して、これらのリソースを解放するための暗黙的な方法と明示的な手段の両方を提供することです。 ガベージコレクターは、オブジェクトが到達できなくなったと判断した後で、オブジェクトの <xref:System.Object.Finalize%2A> メソッドを呼び出します。 @No__t_0 が呼び出された後、オブジェクトを解放するには、追加のガベージコレクションが必要です。 @No__t_0 メソッドを使用すると、呼び出し元は、リソースがガベージコレクターに残されている場合は解放されるのではなく、必要に応じてリソースを明示的に解放できます。 アンマネージリソースをクリーンアップした後、<xref:System.IDisposable.Dispose%2A> は <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> メソッドを呼び出して、<xref:System.Object.Finalize%2A> を呼び出す必要がなくなったことをガベージコレクターに知らせる必要があります。これにより、追加のガベージコレクションが不要になり、オブジェクトの有効期間が短縮されます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、<xref:System.IDisposable> を実装します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 型がアンマネージリソースを参照していない場合は、この規則からの警告を抑制することが安全です。 それ以外の場合は、<xref:System.IDisposable> の実装に失敗すると、アンマネージリソースが使用できなくなったり、使用されなくなったりする可能性があるため、この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例は、アンマネージリソースをクリーンアップするために <xref:System.IDisposable> を実装する型を示しています。

 [!code-csharp[FxCop.Design.UnmanagedResources#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.UnmanagedResources/cs/FxCop.Design.UnmanagedResources.cs#1)]
 [!code-vb[FxCop.Design.UnmanagedResources#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.UnmanagedResources/vb/FxCop.Design.UnmanagedResources.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA2115: ネイティブ リソースを使用しているときには GC.KeepAlive を呼び出します](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)

 [CA1816: GC.SuppressFinalize を正しく呼び出します](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)

 [CA2216: 破棄できる型ではファイナライザーを宣言します](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

 [CA1001: 破棄可能なフィールドを所有する型は、破棄可能でなければなりません](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)

## <a name="see-also"></a>参照
  [Dispose パターン](https://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)
