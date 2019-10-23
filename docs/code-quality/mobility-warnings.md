---
title: モビリティに関する警告
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.MobilityRules
helpviewer_keywords:
- managed code analysis warnings, mobility warnings
- mobility warnings
- warnings, mobility
ms.assetid: 9808054c-593b-4fc3-92cc-1fc45f41569c
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8dedf24f2f6615ec8d24faa0c1e6bc5a48dc2f05
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72649207"
---
# <a name="mobility-warnings"></a>モビリティに関する警告
モビリティの警告は、効率的な電力使用をサポートします。

## <a name="in-this-section"></a>このセクションの内容

|規則|説明|
|----------|-----------------|
|[CA1600: アイドル状態のプロセス優先度を使用しません](../code-quality/ca1600.md)|プロセス優先順位に Idle を設定しないでください。 System.Diagnostics.ProcessPriorityClass.Idle を設定したプロセスは、CPU を占有するか、そうでない場合はアイドル状態になるため、スタンバイ状態がブロックされます。|
|[CA1601: 電源の状態の変更を妨げるタイマーを使用しません](../code-quality/ca1601.md)|定期的な動作の頻度が高くなると、CPU のビジー状態が続き、ディスプレイとハード ディスクをオフにする省電力アイドル タイマーに影響を与えます。|
