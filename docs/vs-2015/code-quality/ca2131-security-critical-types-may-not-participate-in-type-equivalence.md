---
title: 'CA2131: セキュリティ上重要な型は、型の等価性 | に参加できませんMicrosoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2131
ms.assetid: 4170f3b1-6086-430d-8fba-837d5538c573
caps.latest.revision: 12
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 0d32ebc08866a14755ddb8b2c70e2dd0c4ce61f1
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72655494"
---
# <a name="ca2131-security-critical-types-may-not-participate-in-type-equivalence"></a>CA2131: セキュリティ上重要な型は型等価性に参加してはならない
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|CriticalTypesMustNotParticipateInTypeEquivalence|
|CheckId|CA2131|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 型は型の等価性に関与し、型自体、または型のメンバーまたはフィールドのいずれかが、<xref:System.Security.SecurityCriticalAttribute> 属性でマークされています。

## <a name="rule-description"></a>規則の説明
 この規則は、すべての重要な型、または型の等価性に関与する重要なメソッドあるいはフィールドが定義されたすべての型に対して適用されます。 CLR は、このような型を検出すると、実行時に <xref:System.TypeLoadException> の読み込みに失敗します。 通常は、tlbimp やコンパイラによって型の等価性を実装するのではなく、ユーザーが手動で実装した場合に、この規則が適用されます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、SecurityCritical 属性を削除します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例では、この規則を発生させるインターフェイス、メソッド、およびフィールドを示します。

 [!code-csharp[FxCop.Security.CA2131.CriticalTypesMustNotParticipateInTypeEquivalence#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2131.criticaltypesmustnotparticipateintypeequivalence/cs/ca2131 - criticaltypesmustnotparticipateintypeequivalence.cs#1)]

## <a name="see-also"></a>参照
 [透過的セキュリティコード、レベル2](https://msdn.microsoft.com/library/4d05610a-0da6-4f08-acea-d54c9d6143c0)
