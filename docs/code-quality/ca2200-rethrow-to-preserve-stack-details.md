---
title: CA2200:スタック詳細を保持するために再度スローします
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- RethrowToPreserveStackDetails
- CA2200
helpviewer_keywords:
- CA2200
- RethrowToPreserveStackDetails
ms.assetid: 046e1b98-c4dc-4515-874f-9c0de2285621
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 5cf7fc6e31b9250392fc3ea447a5b91225640a50
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231905"
---
# <a name="ca2200-rethrow-to-preserve-stack-details"></a>CA2200:スタック詳細を保持するために再度スローします

|||
|-|-|
|TypeName|RethrowToPreserveStackDetails|
|CheckId|CA2200|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

例外が再スローされ、 `throw`ステートメントで例外が明示的に指定されています。

## <a name="rule-description"></a>規則の説明

例外がスローされると、それに含まれる情報の一部がスタックトレースになります。 スタックトレースは、例外をスローするメソッドで始まり、例外をキャッチするメソッドで終了するメソッド呼び出し階層のリストです。 `throw`ステートメントで例外を指定することによって例外が再スローされた場合、現在のメソッドでスタックトレースが再開され、例外をスローした元のメソッドと現在のメソッドとの間のメソッド呼び出しのリストが失われます。 例外と共に元のスタックトレース情報を保持するに`throw`は、例外を指定せずにステートメントを使用します。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、例外を明示的に指定せずに例外を再スローします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。

## <a name="example"></a>例

次の例は、規則に`CatchAndRethrowExplicitly`違反するメソッドと、規則を満たす`CatchAndRethrowImplicitly`メソッドを示しています。

[!code-csharp[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/CSharp/ca2200-rethrow-to-preserve-stack-details_1.cs)]
[!code-vb[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/VisualBasic/ca2200-rethrow-to-preserve-stack-details_1.vb)]