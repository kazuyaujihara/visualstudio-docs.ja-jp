---
title: CA1009:イベント ハンドラーを正しく宣言します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1009
- DeclareEventHandlersCorrectly
helpviewer_keywords:
- CA1009
- DeclareEventHandlersCorrectly
ms.assetid: ab65c471-1449-49d2-9896-7b9af74284b4
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e923730213ca31a4429d8547fdaaf980692f9a96
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236484"
---
# <a name="ca1009-declare-event-handlers-correctly"></a>CA1009:イベント ハンドラーを正しく宣言します

|||
|-|-|
|TypeName|DeclareEventHandlersCorrectly|
|CheckId|CA1009|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
パブリックまたは保護されたイベントを処理するデリゲートに、正しいシグネチャ、戻り値の型、またはパラメーター名がありません。

## <a name="rule-description"></a>規則の説明
イベント ハンドラー メソッドでは 2 つのパラメーターを使用します。 1つは型<xref:System.Object?displayProperty=fullName>で、は ' sender ' という名前です。 これは、イベントを発生させるオブジェクトです。 2番目のパラメーターの<xref:System.EventArgs?displayProperty=fullName>型はで、' e ' という名前が付けられています。 これは、イベントに関連付けられるデータです。 たとえば、ファイルが開かれるたびにイベントが発生した場合、イベントデータには通常、ファイルの名前が含まれます。

イベントハンドラーメソッドは値を返すことはできません。 C#プログラミング言語では、これは戻り値の型`void`によって示されます。 イベントハンドラーは、複数のオブジェクトで複数のメソッドを呼び出すことができます。 メソッドが値を返すことが許可された場合、各イベントに対して複数の戻り値が発生し、呼び出された最後のメソッドの値のみが使用可能になります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、デリゲートの署名、戻り値の型、またはパラメーター名を修正します。 詳細については、次の例を参照してください。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例は、イベントの処理に適したデリゲートを示しています。 このイベントハンドラーによって呼び出すことができるメソッドは、デザインガイドラインで指定されているシグネチャに準拠しています。 `AlarmEventHandler`デリゲートの型名を指定します。 `AlarmEventArgs`イベントデータ<xref:System.EventArgs>の基本クラスから派生し、アラームイベントデータを保持します。

[!code-cpp[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/CPP/ca1009-declare-event-handlers-correctly_1.cpp)]
[!code-csharp[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/CSharp/ca1009-declare-event-handlers-correctly_1.cs)]
[!code-vb[FxCop.Design.EventsTwoParams#1](../code-quality/codesnippet/VisualBasic/ca1009-declare-event-handlers-correctly_1.vb)]

## <a name="related-rules"></a>関連するルール
[CA2109表示されるイベントハンドラーの確認](../code-quality/ca2109-review-visible-event-handlers.md)

## <a name="see-also"></a>関連項目

- <xref:System.EventArgs?displayProperty=fullName>
- <xref:System.Object?displayProperty=fullName>
- [イベントの処理と発生](/dotnet/standard/events/index)