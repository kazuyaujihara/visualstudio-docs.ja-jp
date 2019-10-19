---
title: 'CA1005: ジェネリック型に対して過剰なパラメーターを避けてください |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
helpviewer_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
ms.assetid: 372b2f28-5c59-4815-9753-6c65b2bb3589
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 7e75b2e295a561e026b437b3c62724536a3ac64e
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671982"
---
# <a name="ca1005-avoid-excessive-parameters-on-generic-types"></a>CA1005: ジェネリック型でパラメーターを使用しすぎないでください
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidExcessiveParametersOnGenericTypes|
|CheckId|CA1005|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 外部から参照できるジェネリック型には、3つ以上の型パラメーターがあります。

## <a name="rule-description"></a>規則の説明
 ジェネリック型に含まれる型パラメーターが増えれば増えるほど、それぞれの型パラメーターが表す意味を調べることや覚えることが難しくなります。 通常は、`List<T>` のように1つの型パラメーターと、`Dictionary<TKey, TValue>` のように2つの型パラメーターを持つ特定のケースでは明らかです。 2つ以上の型パラメーターが存在する場合、ほとんどのユーザーにとって困難になる可能性がC#あります (たとえば、の `TooManyTypeParameters<T, K, V>` や `TooManyTypeParameters(Of T, K, V)` [!INCLUDE[vbprvb](../includes/vbprvb-md.md)])。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、2つ以上の型パラメーターを使用するようにデザインを変更します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 設計に2つ以上の型パラメーターが必要な場合を除き、この規則による警告を抑制しないでください。 簡単に理解して使用できる構文でジェネリックを提供することで、新しいライブラリの導入率を習得し、向上させるために必要な時間を短縮できます。

## <a name="related-rules"></a>関連規則
 [CA1010: コレクションは、ジェネリック インターフェイスを実装しなければなりません](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: ジェネリック型の静的メンバーを宣言しません](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: ジェネリック リストを公開しません](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: ジェネリック型をメンバー シグネチャ内で入れ子にしません](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: ジェネリック メソッドは型パラメーターを指定しなければなりません](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: 汎用イベント ハンドラーのインスタンスを使用します](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: 適切な場所にジェネリックを使用します](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>参照
 [ジェネリック](https://msdn.microsoft.com/library/75ea8509-a4ea-4e7a-a2b3-cf72482e9282)
