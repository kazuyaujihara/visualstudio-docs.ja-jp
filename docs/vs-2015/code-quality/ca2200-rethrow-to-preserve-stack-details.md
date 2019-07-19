---
title: CA2200:スタックの詳細を保持するために再スロー |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RethrowToPreserveStackDetails
- CA2200
helpviewer_keywords:
- CA2200
- RethrowToPreserveStackDetails
ms.assetid: 046e1b98-c4dc-4515-874f-9c0de2285621
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ed2dd2884268511ae05ac89c132f73fdf8b2771e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201635"
---
# <a name="ca2200-rethrow-to-preserve-stack-details"></a>CA2200:スタック詳細を保持するために再度スローします
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|RethrowToPreserveStackDetails|
|CheckId|CA2200|
|Category|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 例外が再スローされ、例外がで明示的に指定されて、`throw`ステートメント。

## <a name="rule-description"></a>規則の説明
 例外がスローされると、スタック トレースは伝達される情報の一部です。 スタック トレースは、例外をスローし、例外をキャッチするメソッドを使用して終了するメソッドで始まるメソッドの呼び出し階層の一覧を示します。 例外を指定することで、例外がスローされます再、`throw`ステートメントでは、スタック トレースは、現在のメソッドに再起動し、例外をスローした元のメソッドと、現在のメソッド間のメソッド呼び出しの一覧は失われます。 例外には、元のスタック トレース情報を保持する使用、`throw`せず、例外を指定するステートメント。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、例外を明示的に指定せず、例外を再スローします。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例では、メソッド、 `CatchAndRethrowExplicitly`、ルールと、メソッドに違反して`CatchAndRethrowImplicitly`規則に適合します。

 [!code-csharp[FxCop.Usage.Rethrow#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.Rethrow/cs/FxCop.Usage.Rethrow.cs#1)]
 [!code-vb[FxCop.Usage.Rethrow#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.Rethrow/vb/FxCop.Usage.Rethrow.vb#1)]
