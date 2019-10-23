---
title: 'CA1021: out パラメーターを回避する |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1021
- AvoidOutParameters
helpviewer_keywords:
- AvoidOutParameters
- CA1021
ms.assetid: 970f2304-842c-4fb7-9734-f3871da8d479
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: ea5d943212122672b84376b9b3ddf5e72bb0e81f
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661995"
---
# <a name="ca1021-avoid-out-parameters"></a>CA1021: out パラメーターを使用しません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidOutParameters|
|CheckId|CA1021|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 パブリック型のパブリックメソッドまたはプロテクトメソッドには `out` パラメーターがあります。

## <a name="rule-description"></a>規則の説明
 (@No__t_0 または `ref` を使用して) 型を参照渡しで渡すには、ポインターの使用経験、値型と参照型の違いの理解、および複数の戻り値を持つメソッドの処理が必要です。 また、`out` パラメーターと `ref` パラメーターの違いはあまり理解されていません。

 参照型が "参照渡し" されると、メソッドは、パラメーターを使用してオブジェクトの別のインスタンスを返すようにします。 参照型を参照渡しで渡すことは、double ポインター、ポインターへのポインター、またはダブル間接参照とも呼ばれます。 既定の呼び出し規約 ("値渡し") を使用すると、参照型を受け取るパラメーターは既にオブジェクトへのポインターを受け取ります。 ポインターが指すオブジェクトではなく、値によって渡されます。 値渡しは、メソッドが参照型の新しいインスタンスを指すようにポインターを変更できないことを意味します。 ただし、ポイントするオブジェクトの内容を変更することができます。 ほとんどのアプリケーションでは、これで十分な動作を実現できます。

 メソッドが別のインスタンスを返す必要がある場合は、メソッドの戻り値を使用してこれを実行します。 文字列を操作し、文字列の新しいインスタンスを返すさまざまなメソッドについては、<xref:System.String?displayProperty=fullName> クラスを参照してください。 このモデルを使用する場合は、元のオブジェクトを保持するかどうかを呼び出し元が決定する必要があります。

 戻り値は一般的であり、頻繁に使用されますが、`out` パラメーターと `ref` パラメーターを適切に適用するには、中間の設計とコーディングのスキルが必要です。 一般ユーザー向けに設計されたライブラリアーキテクトは、ユーザーが `out` または `ref` パラメーターをマスターに使用することを想定してはなりません。

## <a name="how-to-fix-violations"></a>違反の修正方法
 値の型に起因するこの規則違反を修正するには、メソッドが戻り値としてオブジェクトを返すようにします。 メソッドが複数の値を返す必要がある場合は、値を保持するオブジェクトの1つのインスタンスを返すように再設計します。

 参照型に起因するこの規則違反を修正するには、必要な動作が参照の新しいインスタンスを返すことであることを確認します。 この値がの場合、メソッドは戻り値を使用してこれを実行する必要があります。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 このルールからの警告を抑制するのは安全です。 ただし、この設計ではユーザビリティの問題が発生する可能性があります。

## <a name="example"></a>例
 次のライブラリは、ユーザーのフィードバックへの応答を生成するクラスの2つの実装を示しています。 最初の実装 (`BadRefAndOut`) では、ライブラリユーザーが3つの戻り値を管理するように強制します。 2番目の実装 (`RedesignedRefAndOut`) では、データを1つの単位として管理するコンテナークラス (`ReplyData`) のインスタンスを返すことで、ユーザーエクスペリエンスを簡略化します。

 [!code-csharp[FxCop.Design.NoRefOrOut#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.NoRefOrOut/cs/FxCop.Design.NoRefOrOut.cs#1)]

## <a name="example"></a>例
 次のアプリケーションは、ユーザーのエクスペリエンスを示しています。 再設計されたライブラリ (`UseTheSimplifiedClass` メソッド) の呼び出しはより簡単で、メソッドによって返される情報は簡単に管理できます。 2つのメソッドからの出力は同じです。

 [!code-csharp[FxCop.Design.TestNoRefOrOut#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestNoRefOrOut/cs/FxCop.Design.TestNoRefOrOut.cs#1)]

## <a name="example"></a>例
 次のライブラリ例は、参照型のパラメーターを使用する方法を示し、この機能を実装するためのより優れた方法を示しています。 `ref`

 [!code-csharp[FxCop.Design.RefByRefNo#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.RefByRefNo/cs/FxCop.Design.RefByRefNo.cs#1)]

## <a name="example"></a>例
 次のアプリケーションは、ライブラリ内の各メソッドを呼び出して、動作を示します。

 [!code-csharp[FxCop.Design.TestRefByRefNo#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestRefByRefNo/cs/FxCop.Design.TestRefByRefNo.cs#1)]

 この例を実行すると、次の出力が生成されます。

 **値によって渡されたポインターを変更する:** 
**12345** 
**12345** 
**変更ポインターを参照渡し:** 
**12345** 
**12345 abcde...z** 1**戻り値によって渡されます。** 3**12345 abcde...z**
## <a name="try-pattern-methods"></a>Try pattern メソッド

### <a name="description"></a>説明
 @No__t_2 などの**Try \<Something >** パターンを実装するメソッドは、この違反を発生させません。 次の例は、<xref:System.Int32.TryParse%2A?displayProperty=fullName> メソッドを実装する構造体 (値型) を示しています。

### <a name="code"></a>コード
 [!code-csharp[FxCop.Design.TryPattern#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TryPattern/cs/FxCop.Design.TryPattern.cs#1)]

## <a name="related-rules"></a>関連規則
 [CA1045: 型を参照によって渡しません](../code-quality/ca1045-do-not-pass-types-by-reference.md)
