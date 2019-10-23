---
title: 'CA1009: イベントハンドラーを正しく宣言します。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1009
- DeclareEventHandlersCorrectly
helpviewer_keywords:
- CA1009
- DeclareEventHandlersCorrectly
ms.assetid: ab65c471-1449-49d2-9896-7b9af74284b4
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 261013ed844b6c5ba37c544c7745a77378c0c722
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72668919"
---
# <a name="ca1009-declare-event-handlers-correctly"></a>CA1009: イベント ハンドラーを正しく宣言します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DeclareEventHandlersCorrectly|
|CheckId|CA1009|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 パブリックまたは保護されたイベントを処理するデリゲートに、正しいシグネチャ、戻り値の型、またはパラメーター名がありません。

## <a name="rule-description"></a>規則の説明
 イベント ハンドラー メソッドでは 2 つのパラメーターを使用します。 1つ目は <xref:System.Object?displayProperty=fullName> 型で、' sender ' という名前が付けられます。 これは、イベントを発生させるオブジェクトです。 2番目のパラメーターは <xref:System.EventArgs?displayProperty=fullName> 型で、' e ' という名前が付けられています。 これは、イベントに関連付けられるデータです。 たとえば、ファイルが開かれるたびにイベントが発生した場合、イベントデータには通常、ファイルの名前が含まれます。

 イベントハンドラーメソッドは値を返すことはできません。 C#プログラミング言語では、これは戻り値の型 `void` によって示されます。 イベントハンドラーは、複数のオブジェクトで複数のメソッドを呼び出すことができます。 メソッドが値を返すことが許可された場合、各イベントに対して複数の戻り値が発生し、呼び出された最後のメソッドの値のみが使用可能になります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、デリゲートの署名、戻り値の型、またはパラメーター名を修正します。 詳細については、次の例を参照してください。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例は、イベントの処理に適したデリゲートを示しています。 このイベントハンドラーによって呼び出すことができるメソッドは、デザインガイドラインで指定されているシグネチャに準拠しています。 `AlarmEventHandler` は、デリゲートの型名です。 `AlarmEventArgs` は、イベントデータの基底クラスから派生し、<xref:System.EventArgs>、およびアラームイベントデータを保持します。

 [!code-cpp[FxCop.Design.EventsTwoParams#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.EventsTwoParams/cpp/FxCop.Design.EventsTwoParams.cpp#1)]
 [!code-csharp[FxCop.Design.EventsTwoParams#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EventsTwoParams/cs/FxCop.Design.EventsTwoParams.cs#1)]
 [!code-vb[FxCop.Design.EventsTwoParams#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.EventsTwoParams/vb/FxCop.Design.EventsTwoParams.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA2109: 表示するイベント ハンドラーをレビューします](../code-quality/ca2109-review-visible-event-handlers.md)

## <a name="see-also"></a>参照
 <xref:System.EventArgs?displayProperty=fullName> <xref:System.Object?displayProperty=fullName>
 [NIB: イベントとデリゲート](https://msdn.microsoft.com/d98fd58b-fa4f-4598-8378-addf4355a115)
