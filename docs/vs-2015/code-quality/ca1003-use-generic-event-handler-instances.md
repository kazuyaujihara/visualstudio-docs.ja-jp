---
title: CA1003:汎用イベント ハンドラーのインスタンスを使用して、|Microsoft Docs
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
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 25c96abd08f9d6c5f519c5f897c43aaf28bc231b
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65682274"
---
# <a name="ca1003-use-generic-event-handler-instances"></a>CA1003:汎用イベント ハンドラーのインスタンスを使用します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseGenericEventHandlerInstances|
|CheckId|CA1003|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 型が void を返す、2 つのパラメーター (1 つはオブジェクトと、2 つ目は EventArgs に割り当て可能な型) と包含アセンブリの対象を含むシグネチャを持つデリゲートを含む[!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)]します。

## <a name="rule-description"></a>規則の説明
 前に[!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)]、イベント ハンドラーにカスタム情報を渡すために、新しいデリゲートを宣言から派生したクラスを指定する必要がある、<xref:System.EventArgs?displayProperty=fullName>クラス。 場合は true。 これは不要になった[!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)]、導入された、<xref:System.EventHandler%601?displayProperty=fullName>を委任します。 この汎用デリゲートにより、任意のクラスから派生した<xref:System.EventArgs>イベント ハンドラーと共に使用します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則の違反を修正するには、デリゲートを削除しを使用してその使用を置き換える、<xref:System.EventHandler%601?displayProperty=fullName>を委任します。 デリゲートがによって自動生成された場合、[!INCLUDE[vbprvb](../includes/vbprvb-md.md)]コンパイラを使用するイベントの宣言の構文を変更、<xref:System.EventHandler%601?displayProperty=fullName>を委任します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例では、規則に違反するデリゲートを示します。 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]例では、コメント、ルールを満たすために例を変更する方法を示しています。 例では、c# の例で、変更されたコードが表示されるに従います。

 [!code-csharp[FxCop.Design.CustomEventHandler#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.CustomEventHandler/cs/FxCop.Design.CustomEventHandler.cs#1)]
 [!code-vb[FxCop.Design.CustomEventHandler#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.CustomEventHandler/vb/FxCop.Design.CustomEventHandler.vb#1)]

## <a name="example"></a>例
 次の例では、デリゲート宣言を削除で使用し、ルールを満たす前の例から、`ClassThatRaisesEvent`と`ClassThatHandlesEvent`メソッドを使用して、<xref:System.EventHandler%601?displayProperty=fullName>を委任します。

 [!code-csharp[FxCop.Design.GenericEventHandler#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.GenericEventHandler/cs/FxCop.Design.GenericEventHandler.cs#1)]

## <a name="related-rules"></a>関連規則
 [CA1005:ジェネリック型で過剰なパラメーターを回避します。](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA 1010:コレクションは、ジェネリック インターフェイスを実装する必要があります。](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA 1000:ジェネリック型で静的メンバーを宣言しません](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA 1002:ジェネリック リストを公開しません](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA 1006:ジェネリック型メンバー シグネチャ内で入れ子にしません](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA 1004:ジェネリック メソッドは、型パラメーターを指定する必要があります。](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA 1007:適切な場所にジェネリックを使用します。](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>関連項目
 [ジェネリック](https://msdn.microsoft.com/library/75ea8509-a4ea-4e7a-a2b3-cf72482e9282)
