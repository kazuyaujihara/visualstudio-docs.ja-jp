---
title: 'CA1003: 汎用イベントハンドラーのインスタンスを使用します。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseGenericEventHandlerInstances
- CA1003
helpviewer_keywords:
- CA1003
- UseGenericEventHandlerInstances
ms.assetid: 402101b6-555d-4cf7-b223-1d9fdfaaf1cd
caps.latest.revision: 24
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 34318d3fb01f3f8dee50da2bc534908cecbdaf32
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72646298"
---
# <a name="ca1003-use-generic-event-handler-instances"></a>CA1003: 汎用イベント ハンドラーのインスタンスを使用します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseGenericEventHandlerInstances|
|CheckId|CA1003|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 型には、void を返すデリゲートが含まれています。このシグネチャには、2つのパラメーター (最初のオブジェクト、もう1つは EventArgs に割り当て可能な型)、および包含するアセンブリターゲット [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)] が含まれています。

## <a name="rule-description"></a>規則の説明
 @No__t_0 する前に、カスタム情報をイベントハンドラーに渡すために、<xref:System.EventArgs?displayProperty=fullName> クラスから派生したクラスを指定した新しいデリゲートを宣言する必要がありました。 これは、<xref:System.EventHandler%601?displayProperty=fullName> デリゲートを導入した [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)] ではなくなりました。 この汎用デリゲートを使用すると、<xref:System.EventArgs> から派生した任意のクラスをイベントハンドラーと共に使用できます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、デリゲートを削除し、<xref:System.EventHandler%601?displayProperty=fullName> デリゲートを使用してデリゲートを置き換えます。 デリゲートが [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] コンパイラによって自動生成される場合は、<xref:System.EventHandler%601?displayProperty=fullName> デリゲートを使用するようにイベント宣言の構文を変更します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例は、規則に違反するデリゲートを示しています。 @No__t_0 の例では、この例を変更してルールを満たす方法を説明しています。 C#例では、変更されたコードを表示する例を次に示します。

 [!code-csharp[FxCop.Design.CustomEventHandler#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.CustomEventHandler/cs/FxCop.Design.CustomEventHandler.cs#1)]
 [!code-vb[FxCop.Design.CustomEventHandler#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.CustomEventHandler/vb/FxCop.Design.CustomEventHandler.vb#1)]

## <a name="example"></a>例
 次の例では、ルールを満たす前の例からデリゲート宣言を削除し、<xref:System.EventHandler%601?displayProperty=fullName> デリゲートを使用して、`ClassThatRaisesEvent` および `ClassThatHandlesEvent` メソッドでの使用を置き換えます。

 [!code-csharp[FxCop.Design.GenericEventHandler#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.GenericEventHandler/cs/FxCop.Design.GenericEventHandler.cs#1)]

## <a name="related-rules"></a>関連規則
 [CA1005: ジェネリック型でパラメーターを使用しすぎないでください](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: コレクションは、ジェネリック インターフェイスを実装しなければなりません](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: ジェネリック型の静的メンバーを宣言しません](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: ジェネリック リストを公開しません](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: ジェネリック型をメンバー シグネチャ内で入れ子にしません](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: ジェネリック メソッドは型パラメーターを指定しなければなりません](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1007: 適切な場所にジェネリックを使用します](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>参照
 [ジェネリック](https://msdn.microsoft.com/library/75ea8509-a4ea-4e7a-a2b3-cf72482e9282)
