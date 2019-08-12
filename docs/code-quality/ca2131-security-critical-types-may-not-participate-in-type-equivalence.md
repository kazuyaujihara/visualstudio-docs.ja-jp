---
title: CA2131:セキュリティ上重要な型は型等価性に参加してはならない
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2131
ms.assetid: 4170f3b1-6086-430d-8fba-837d5538c573
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 521a44b432a5b8ea886b23aab6b39789efe3b1b0
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920702"
---
# <a name="ca2131-security-critical-types-may-not-participate-in-type-equivalence"></a>CA2131:セキュリティ上重要な型は型等価性に参加してはならない

|||
|-|-|
|TypeName|CriticalTypesMustNotParticipateInTypeEquivalence|
|CheckId|CA2131|
|Category|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
型は型の等価性に関与し、型自体、または型のメンバーまたはフィールドのいずれかが<xref:System.Security.SecurityCriticalAttribute>属性でマークされます。

## <a name="rule-description"></a>規則の説明
この規則は、すべての重要な型、または型の等価性に関与する重要なメソッドあるいはフィールドが定義されたすべての型に対して適用されます。 CLR は、このような型を検出すると、実行時に<xref:System.TypeLoadException>を使用してそれを読み込むことができません。 通常は、tlbimp やコンパイラによって型の等価性を実装するのではなく、ユーザーが手動で実装した場合に、この規則が適用されます。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、SecurityCritical 属性を削除します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。

## <a name="example"></a>例
次の例では、この規則を発生させるインターフェイス、メソッド、およびフィールドを示します。

[!code-csharp[FxCop.Security.CA2131.CriticalTypesMustNotParticipateInTypeEquivalence#1](../code-quality/codesnippet/CSharp/ca2131-security-critical-types-may-not-participate-in-type-equivalence_1.cs)]

## <a name="see-also"></a>関連項目
[透過的セキュリティコード、レベル2](/dotnet/framework/misc/security-transparent-code-level-2)