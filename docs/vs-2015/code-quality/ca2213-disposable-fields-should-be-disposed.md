---
title: 'CA2213: 破棄可能なフィールドを破棄する必要があります |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DisposableFieldsShouldBeDisposed
- CA2213
helpviewer_keywords:
- CA2213
- DisposableFieldsShouldBeDisposed
ms.assetid: e99442c9-70e2-47f3-b61a-d8ac003bc6e5
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 8ebeae3e5e367bb2c1a09bc1cb38dcc80d2c3826
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72662894"
---
# <a name="ca2213-disposable-fields-should-be-disposed"></a>CA2213: 破棄可能なフィールドは破棄されなければなりません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DisposableFieldsShouldBeDisposed|
|CheckId|CA2213|
|カテゴリ|Microsoft. 使用方法|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 @No__t_1 を実装する型のフィールドを宣言 <xref:System.IDisposable?displayProperty=fullName> を実装する型。 フィールドの <xref:System.IDisposable.Dispose%2A> メソッドが、宣言する型の <xref:System.IDisposable.Dispose%2A> メソッドによって呼び出されていません。

## <a name="rule-description"></a>規則の説明
 型は、そのすべてのアンマネージリソースを破棄します。これは <xref:System.IDisposable> を実装することで実現されます。 このルールでは、破棄可能な型 `T` が、破棄可能な型 `FT` のインスタンスであるフィールド `F` 宣言しているかどうかを確認します。 フィールド `F` ごとに、ルールは `FT.Dispose` の呼び出しを検索します。 このルールは、`T.Dispose` によって呼び出されたメソッドと、1レベル下 (`FT.Dispose` によって呼び出されたメソッドによって呼び出されたメソッド) を検索します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、フィールドに保持されているアンマネージリソースの割り当てと解放を担当する場合は、<xref:System.IDisposable> を実装する型のフィールドに対して <xref:System.IDisposable.Dispose%2A> を呼び出します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 フィールドに保持されているリソースを解放する責任がない場合、または <xref:System.IDisposable.Dispose%2A> の呼び出しが規則のチェックよりも詳細な呼び出しレベルで発生する場合は、この規則からの警告を抑制するのが安全です。

## <a name="example"></a>例
 次の例は、<xref:System.IDisposable> (前の説明の `FT`) を実装する `TypeA` 型を示しています。

 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.IDisposablePattern/cs/FxCop.Usage.IDisposablePattern.cs#1)]

## <a name="example"></a>例
 次の例は、フィールド `aFieldOfADisposableType` (前の説明の `F`) を破棄可能な型 (`TypeA`) として宣言し、フィールドで <xref:System.IDisposable.Dispose%2A> を呼び出さないことによって、この規則に違反する型 `TypeB` を示しています。 `TypeB` は、前の説明の `T` に対応します。

 [!code-csharp[FxCop.Usage.IDisposableFields#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.IDisposableFields/cs/FxCop.Usage.IDisposableFields.cs#1)]

## <a name="see-also"></a>参照
 <xref:System.IDisposable?displayProperty=fullName> [Dispose パターン](https://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)
