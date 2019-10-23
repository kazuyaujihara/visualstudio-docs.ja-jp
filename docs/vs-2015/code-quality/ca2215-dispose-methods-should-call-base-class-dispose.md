---
title: 'CA2215: Dispose メソッドは基底クラスの dispose | を呼び出す必要がありますMicrosoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2215
- DisposeMethodsShouldCallBaseClassDispose
- Dispose methods should call base class dispose
helpviewer_keywords:
- DisposeMethodsShouldCallBaseClassDispose
- CA2215
ms.assetid: c772e7a6-a87e-425c-a70e-912664ae9042
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 89f3705169fb9d28a1ec773671d460f00b98d892
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72662859"
---
# <a name="ca2215-dispose-methods-should-call-base-class-dispose"></a>CA2215: Dispose メソッドから基本クラスの破棄を呼び出します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DisposeMethodsShouldCallBaseClassDispose|
|CheckId|CA2215|
|カテゴリ|Microsoft. 使用方法|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 @No__t_0 を実装する型は、<xref:System.IDisposable> も実装する型から継承されます。 継承する型の <xref:System.IDisposable.Dispose%2A> メソッドは、親の型の <xref:System.IDisposable.Dispose%2A> メソッドを呼び出しません。

## <a name="rule-description"></a>規則の説明
 型が破棄可能な型から継承する場合は、独自の <xref:System.IDisposable.Dispose%2A> メソッド内から基本型の <xref:System.IDisposable.Dispose%2A> メソッドを呼び出す必要があります。 基本型のメソッド Dispose を呼び出すと、基本型によって作成されたすべてのリソースが解放されます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、`base` を呼び出します。<xref:System.IDisposable.Dispose%2A> <xref:System.IDisposable.Dispose%2A> メソッド内。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 @No__t_0 を呼び出すと、この規則からの警告を抑制するのが安全です。<xref:System.IDisposable.Dispose%2A> ルールチェックよりも深い呼び出しレベルで発生します。

## <a name="example"></a>例
 次の例は、<xref:System.IDisposable> を実装する型 `TypeA` を示しています。

 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.IDisposablePattern/cs/FxCop.Usage.IDisposablePattern.cs#1)]

## <a name="example"></a>例
 次の例は、型 `TypeA` から継承し、その <xref:System.IDisposable.Dispose%2A> メソッドを正しく呼び出す `TypeB` 型を示しています。

 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.IDisposableBaseCalled/vb/FxCop.Usage.IDisposableBaseCalled.vb#1)]

## <a name="see-also"></a>参照
 <xref:System.IDisposable?displayProperty=fullName> [Dispose パターン](https://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)
