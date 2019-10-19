---
title: 'CA1816: GC を呼び出します。Gc.suppressfinalize を正しく |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1816
- DisposeMethodsShouldCallSuppressFinalize
helpviewer_keywords:
- DisposeMethodsShouldCallSuppressFinalize
- CA1816
ms.assetid: 47915fbb-103f-4333-b157-1da16bf49660
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: acc86c278faa877897d294e72632762eff834a76
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72668386"
---
# <a name="ca1816-call-gcsuppressfinalize-correctly"></a>CA1816: GC.SuppressFinalize を正しく呼び出します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|CallGCSuppressFinalizeCorrectly|
|CheckId|CA1816|
|カテゴリ|エクスプローラー. 使用方法|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

- @No__t_0 の実装であるメソッドは、<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> を呼び出しません。

- @No__t_0 の実装ではないメソッドは <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> を呼び出します。

- メソッドは <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> を呼び出し、この以外のもの (Visual Basic では) を渡します。

## <a name="rule-description"></a>規則の説明
 @No__t_0 メソッドを使用すると、オブジェクトがガベージコレクションに使用できるようになる前に、いつでもユーザーがリソースを解放できます。 @No__t_0 メソッドが呼び出されると、オブジェクトのリソースが解放されます。 これにより、終了処理は不要になります。 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> は、ガベージコレクターがオブジェクトのファイナライザーを呼び出さないように <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> を呼び出す必要があります。

 ファイナライザーの派生型が [system.object] を再実装しないようにするには (<!-- TODO: review code entity reference <xref:assetId:///System.IDisposable?qualifyHint=True&amp;autoUpgrade=False>  -->) を呼び出すために、ファイナライザーのないシールされていない型は引き続き <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> を呼び出す必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、次のようにします。

 メソッドが <xref:System.IDisposable.Dispose%2A> の実装である場合は、<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> への呼び出しを追加します。

 メソッドが <xref:System.IDisposable.Dispose%2A> の実装でない場合は、<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> への呼び出しを削除するか、型の <xref:System.IDisposable.Dispose%2A> 実装に移動します。

 @No__t_0 のすべての呼び出しを変更して、この (Visual Basic) を渡します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 @No__t_0 を使用して他のオブジェクトの有効期間を制御する場合にのみ、このルールからの警告を抑制します。 @No__t_0 の実装で <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> が呼び出されない場合は、この規則による警告を抑制しないでください。 このような状況では、終了処理を抑制しないとパフォーマンスが低下し、利点は得られません。

## <a name="example"></a>例
 次の例は、<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> を誤って呼び出すメソッドを示しています。

 [!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.CallGCSuppressFinalizeCorrectly/CS/FxCop.Usage.CallGCSuppressFinalizeCorrectly.cs#1)]
 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.CallGCSuppressFinalizeCorrectly/VB/FxCop.Usage.CallGCSuppressFinalizeCorrectly.vb#1)]

## <a name="example"></a>例
 次の例は、<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> を正しく呼び出すメソッドを示しています。

 [!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.CallGCSuppressFinalizeCorrectly2/CS/FxCop.Usage.CallGCSuppressFinalizeCorrectly2.cs#1)]
 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.CallGCSuppressFinalizeCorrectly2/VB/FxCop.Usage.CallGCSuppressFinalizeCorrectly2.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA2215: Dispose メソッドから基本クラスの破棄を呼び出します](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)

 [CA2216: 破棄できる型ではファイナライザーを宣言します](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

## <a name="see-also"></a>参照
 [Dispose パターン](https://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)
