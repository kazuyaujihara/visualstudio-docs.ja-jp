---
title: 'CA2220: ファイナライザーは基底クラスのファイナライザー | を呼び出す必要がありますMicrosoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
helpviewer_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
ms.assetid: 48329f42-170d-45ee-a381-e33f55a240c5
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 1a4538c66d351956da8168d4f84c1895190ab453
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663589"
---
# <a name="ca2220-finalizers-should-call-base-class-finalizer"></a>CA2220: ファイナライザーは基本クラスのファイナライザーを呼び出さなければなりません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|FinalizersShouldCallBaseClassFinalizer|
|CheckId|CA2220|
|カテゴリ|Microsoft. 使用方法|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 @No__t_0 をオーバーライドする型は、基本クラスの <xref:System.Object.Finalize%2A> メソッドを呼び出しません。

## <a name="rule-description"></a>規則の説明
 終了処理は、継承の階層構造を使用して反映する必要があります。 これを実現するには、型が独自の <xref:System.Object.Finalize%2A> メソッド内から基本クラス <xref:System.Object.Finalize%2A> メソッドを呼び出す必要があります。 コンパイラC#は、基本クラスのファイナライザーに自動的に呼び出しを追加します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、<xref:System.Object.Finalize%2A> メソッドから基本型の <xref:System.Object.Finalize%2A> メソッドを呼び出します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。 共通言語ランタイムを対象とする一部のコンパイラは、基本型のファイナライザーへの呼び出しを Microsoft 中間言語 (MSIL) に挿入します。 この規則からの警告が報告された場合、コンパイラは呼び出しを挿入せず、コードに追加する必要があります。

## <a name="example"></a>例
 次の Visual Basic 例は、基本クラスで <xref:System.Object.Finalize%2A> メソッドを正しく呼び出す型 `TypeB` を示しています。

 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.IDisposableBaseCalled/vb/FxCop.Usage.IDisposableBaseCalled.vb#1)]

## <a name="see-also"></a>参照
 [Dispose パターン](https://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)
