---
title: 'CA1600: アイドル状態のプロセス優先度を使用しない |Microsoft Docs'
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
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: d4260db808d9c50f78388cf6ba976f7ace52e6a3
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72669293"
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600: アイドル状態のプロセス優先度を使用しません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotUseIdleProcessPriority|
|CheckId|CA1600|
|カテゴリ|Microsoft モビリティ|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 このルールは、プロセスが `ProcessPriorityClass.Idle` に設定されている場合に発生します。

## <a name="rule-description"></a>規則の説明
 プロセス優先順位に Idle を設定しないでください。 @No__t_0 を持つプロセスは、CPU がアイドル状態になると CPU を占有するため、スタンバイをブロックします。

## <a name="how-to-fix-violations"></a>違反の修正方法
 プロセスを `ProcessPriorityClass.BelowNormal` に設定します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 このルールは、アイドル状態のプロセスの優先順位が必要で、モビリティに関する考慮事項を安全に無視できる場合にのみ抑制する必要があります。
