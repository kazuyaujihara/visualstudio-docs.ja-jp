---
title: CA1600:アイドル状態のプロセスの優先順位を使用しないでください |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotUseIdleProcessPriority
- CA1600
helpviewer_keywords:
- CA1600
- DoNotUseIdleProcessPriority
ms.assetid: 9b0d073b-78b6-41be-8ef3-14692a735283
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 4002e17e3988ca3b449e141394ce762f95ffc78b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68189301"
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600:アイドル状態のプロセス優先度を使用しません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotUseIdleProcessPriority|
|CheckId|CA1600|
|Category|Microsoft.Mobility|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 このルールは、プロセスに設定されているときに発生します。`ProcessPriorityClass.Idle`します。

## <a name="rule-description"></a>規則の説明
 プロセス優先順位に Idle を設定しないでください。 持つプロセス`System.Diagnostics.ProcessPriorityClass.Idle`アイドル状態になるし、スタンバイをブロックするために、CPU を占有します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 プロセスを設定`ProcessPriorityClass.BelowNormal`します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 アイドル状態のプロセスの優先度が必要で、モビリティに関する考慮事項を安全に無視できる場合にのみ、このルールを抑制する必要があります。
