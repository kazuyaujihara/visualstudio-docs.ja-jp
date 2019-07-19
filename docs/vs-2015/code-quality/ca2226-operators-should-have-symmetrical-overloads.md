---
title: CA2226:演算子は対称型オーバー ロードが必要 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
helpviewer_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
ms.assetid: d202401a-ea14-4559-b15e-0ea4f5b68789
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 574f254b1cfccf58def5c404c15b03a4c83658cc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68142445"
---
# <a name="ca2226-operators-should-have-symmetrical-overloads"></a>CA2226:演算子は対称型オーバーロードを含まなければなりません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|OperatorsShouldHaveSymmetricalOverloads|
|CheckId|CA2226|
|Category|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 型で等値演算子または非等値演算子を実装し、逆の働きをする演算子を実装していません。

## <a name="rule-description"></a>規則の説明
 等値または非等値のいずれかを型のインスタンスに適用できますが、反対側の演算子が定義されての状況ではありません。 型は、通常、等値演算子の符号が逆の値を返すことによって、非等値演算子を実装します。

 C# コンパイラでは、この規則の違反のエラーを発行します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するのには、等しいかどうかと非等値演算子の両方を実装または存在する 1 つを削除します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。 一貫性のある方法では、型は機能しません、[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]します。

## <a name="related-rules"></a>関連規則
 [CA1046:参照型で、演算子 equals をオーバー ロードしません。](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2225:演算子のオーバー ロード名前付けされた代替](../code-quality/ca2225-operator-overloads-have-named-alternates.md)

 [CA2224:オーバー ロードする演算子 equals で equals をオーバーライド](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2218:Equals をオーバーライドの GetHashCode をオーバーライドします。](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

 [CA2231: ValueType.Equals のオーバーライドで、演算子 equals をオーバーロードします](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)
