---
title: CA2220:ファイナライザーは基底クラスのファイナライザーを呼び出さなければなりません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
helpviewer_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
ms.assetid: 48329f42-170d-45ee-a381-e33f55a240c5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e5af6b7872f0fa05183334e6acd2bc4922f84990
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231161"
---
# <a name="ca2220-finalizers-should-call-base-class-finalizer"></a>CA2220:ファイナライザーは基底クラスのファイナライザーを呼び出さなければなりません

|||
|-|-|
|TypeName|FinalizersShouldCallBaseClassFinalizer|
|CheckId|CA2220|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

をオーバーライド<xref:System.Object.Finalize%2A?displayProperty=fullName>する型は、その基底<xref:System.Object.Finalize%2A>クラスのメソッドを呼び出しません。

## <a name="rule-description"></a>規則の説明

終了処理は、継承の階層構造を使用して反映する必要があります。 これを実現するには、型は独自<xref:System.Object.Finalize%2A> <xref:System.Object.Finalize%2A>のメソッド内から基底クラスのメソッドを呼び出す必要があります。 コンパイラC#は、基本クラスのファイナライザーに自動的に呼び出しを追加します。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、 <xref:System.Object.Finalize%2A> <xref:System.Object.Finalize%2A>メソッドから基本型のメソッドを呼び出します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。 共通言語ランタイムを対象とする一部のコンパイラは、基本型のファイナライザーへの呼び出しを Microsoft 中間言語 (MSIL) に挿入します。 この規則からの警告が報告された場合、コンパイラは呼び出しを挿入せず、コードに追加する必要があります。

## <a name="example"></a>例

次の Visual Basic 例は、基底`TypeB`クラスで<xref:System.Object.Finalize%2A>メソッドを正しく呼び出す型を示しています。

[!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2220-finalizers-should-call-base-class-finalizer_1.vb)]

## <a name="see-also"></a>関連項目

- [Dispose パターン](/dotnet/standard/design-guidelines/dispose-pattern)