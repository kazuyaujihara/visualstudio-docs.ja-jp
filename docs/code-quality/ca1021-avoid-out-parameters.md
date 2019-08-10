---
title: CA1021:out パラメーターを使用しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1021
- AvoidOutParameters
helpviewer_keywords:
- AvoidOutParameters
- CA1021
ms.assetid: 970f2304-842c-4fb7-9734-f3871da8d479
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cf9475ad208a229057700fa2965984fbdcb17abf
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923099"
---
# <a name="ca1021-avoid-out-parameters"></a>CA1021:out パラメーターを使用しません

|||
|-|-|
|TypeName|AvoidOutParameters|
|CheckId|CA1021|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
パブリック型のパブリックメソッドまたはプロテクトメソッドには`out` 、パラメーターがあります。

## <a name="rule-description"></a>規則の説明
型を参照渡しで渡す`out` ( `ref`またはを使用) には、ポインターの使用経験、値型と参照型の違いの理解、および複数の戻り値を持つメソッドの処理が必要です。 また、パラメーターと`out` `ref`パラメーターの違いは広く認識されていません。

参照型が "参照渡し" されると、メソッドは、パラメーターを使用してオブジェクトの別のインスタンスを返すようにします。 参照型を参照渡しで渡すことは、double ポインター、ポインターへのポインター、またはダブル間接参照とも呼ばれます。 既定の呼び出し規約 ("値渡し") を使用すると、参照型を受け取るパラメーターは既にオブジェクトへのポインターを受け取ります。 ポインターが指すオブジェクトではなく、値によって渡されます。 値渡しは、メソッドが参照型の新しいインスタンスを指すようにポインターを変更できないことを意味します。 ただし、ポイントするオブジェクトの内容を変更することができます。 ほとんどのアプリケーションでは、これで十分な動作を実現できます。

メソッドが別のインスタンスを返す必要がある場合は、メソッドの戻り値を使用してこれを実行します。 文字列を操作し、文字列の新しいインスタンスを返すさまざまなメソッドについては、クラスを参照してください。<xref:System.String?displayProperty=fullName> このモデルを使用する場合は、元のオブジェクトを保持するかどうかを呼び出し元が決定する必要があります。

戻り値は一般的であり、頻繁に使用されます`out`が`ref` 、パラメーターとパラメーターを正しく適用するには、中間の設計とコーディングのスキルが必要です。 一般ユーザー向けに設計されたライブラリアーキテクトは、ユーザーがまたは`out` `ref`パラメーターをマスターに使用することを想定しないでください。

## <a name="how-to-fix-violations"></a>違反の修正方法
値の型に起因するこの規則違反を修正するには、メソッドが戻り値としてオブジェクトを返すようにします。 メソッドが複数の値を返す必要がある場合は、値を保持するオブジェクトの1つのインスタンスを返すように再設計します。

参照型に起因するこの規則違反を修正するには、必要な動作が参照の新しいインスタンスを返すことであることを確認します。 この値がの場合、メソッドは戻り値を使用してこれを実行する必要があります。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
このルールからの警告を抑制するのは安全です。 ただし、この設計ではユーザビリティの問題が発生する可能性があります。

## <a name="example"></a>例
次のライブラリは、ユーザーのフィードバックへの応答を生成するクラスの2つの実装を示しています。 最初の実装 (`BadRefAndOut`) では、ライブラリユーザーが3つの戻り値を管理するように強制します。 2番目の`RedesignedRefAndOut`実装 () は、データを1つの単位として`ReplyData`管理するコンテナークラス () のインスタンスを返すことによって、ユーザーエクスペリエンスを簡略化します。

[!code-csharp[FxCop.Design.NoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_1.cs)]

## <a name="example"></a>例
次のアプリケーションは、ユーザーのエクスペリエンスを示しています。 再設計されたライブラリ (`UseTheSimplifiedClass`メソッド) の呼び出しはより簡単で、メソッドによって返される情報は簡単に管理できます。 2つのメソッドからの出力は同じです。

[!code-csharp[FxCop.Design.TestNoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_2.cs)]

## <a name="example"></a>例
次のライブラリ例は、 `ref`参照型のパラメーターを使用する方法を示しています。また、この機能を実装するためのより良い方法を示しています。

[!code-csharp[FxCop.Design.RefByRefNo#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_3.cs)]

## <a name="example"></a>例
次のアプリケーションは、ライブラリ内の各メソッドを呼び出して、動作を示します。

[!code-csharp[FxCop.Design.TestRefByRefNo#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_4.cs)]

この例を実行すると、次の出力が生成されます。

```txt
Changing pointer - passed by value:
12345
12345
Changing pointer - passed by reference:
12345
12345 ABCDE
Passing by return value:
12345 ABCDE
```

## <a name="try-pattern-methods"></a>Try pattern メソッド

### <a name="description"></a>説明
<xref:System.Int32.TryParse%2A?displayProperty=fullName>のような**Try \<Something>** パターンを実装するメソッドではこの違反を起こさないでください。 次の例は、<xref:System.Int32.TryParse%2A?displayProperty=fullName>メソッドを実装する構造体 (値型)を示します。

### <a name="code"></a>コード
[!code-csharp[FxCop.Design.TryPattern#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_5.cs)]

## <a name="related-rules"></a>関連するルール
[CA1045型を参照渡しで渡すことはできません](../code-quality/ca1045-do-not-pass-types-by-reference.md)