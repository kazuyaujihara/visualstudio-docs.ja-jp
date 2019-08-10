---
title: CA1601:電源の状態の変更を妨げるタイマーを使用しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
helpviewer_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
ms.assetid: b8028c92-0696-4c54-9773-0028f29bda9a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6b3c3fe41332d488d180ddafbedfe29da1a3855e
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921789"
---
# <a name="ca1601-do-not-use-timers-that-prevent-power-state-changes"></a>CA1601:電源の状態の変更を妨げるタイマーを使用しません

|||
|-|-|
|TypeName|DoNotUseTimersThatPreventPowerStateChanges|
|CheckId|CA1601|
|Category|Microsoft モビリティ|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
タイマーの間隔が1秒間に複数回発生するように設定されています。

## <a name="rule-description"></a>規則の説明
1秒間に複数回ポーリングしたり、1秒間に1回以上発生するタイマーを使用したりしないでください。 定期的な動作の頻度が高くなると、CPU のビジー状態が続き、ディスプレイとハード ディスクをオフにする省電力アイドル タイマーに影響を与えます。

## <a name="how-to-fix-violations"></a>違反の修正方法
タイマー間隔を1秒あたり1回未満に設定します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
このルールは、タイマーを1秒間に複数回実行する必要があり、モビリティに関する考慮事項を無視しても問題がない場合にのみ抑制する必要があります。