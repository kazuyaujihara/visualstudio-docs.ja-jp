---
title: CA2219:exception 句に例外を発生させないでください
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
helpviewer_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
ms.assetid: 7b9b0bee-4e8e-49a4-8c40-52142b49061f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2f8e949e21530654882cba99a7d9fedad8b5b59b
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920264"
---
# <a name="ca2219-do-not-raise-exceptions-in-exception-clauses"></a>CA2219:exception 句に例外を発生させないでください

|||
|-|-|
|TypeName|DoNotRaiseExceptionsInExceptionClauses|
|CheckId|CA2219|
|Category|Microsoft.Usage|
|互換性に影響する変更点|中断しない、中断|

## <a name="cause"></a>原因
`finally`、Filter、または fault 句から例外がスローされます。

## <a name="rule-description"></a>規則の説明
例外句で例外が発生すると、デバッグの難易度が大幅に向上します。

`finally`または fault 句で例外が発生すると、新しい例外によってアクティブな例外が非表示になります (存在する場合)。 これにより、元のエラーの検出とデバッグが困難になります。

フィルター句で例外が発生すると、ランタイムはその例外をサイレントにキャッチし、フィルターを false に評価します。 フィルターが false と評価され、フィルターによって例外がスローされるという違いを通知する方法はありません。 これにより、フィルターのロジックでエラーを検出してデバッグすることが難しくなります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、 `finally`、filter、または fault 句から明示的に例外を発生させないようにします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
このルールの警告を抑制しないでください。 例外句で発生した例外によって実行コードに利点が得られるシナリオはありません。

## <a name="related-rules"></a>関連するルール
[CA1065予期しない場所で例外を発生させない](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)

## <a name="see-also"></a>関連項目
[デザインの警告](../code-quality/design-warnings.md)