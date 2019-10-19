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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3fecdc2f6e7ab8015bf56f38ee00c9bb43a3b38c
ms.sourcegitcommit: 08c144d290da373df841f04fc799e3133540a541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72535756"
---
# <a name="mobility-warnings"></a>モビリティに関する警告
モビリティの警告は、効率的な電力使用をサポートします。

## <a name="in-this-section"></a>このセクションの内容

|規則|説明|
|----------|-----------------|
|[CA1600: アイドル状態のプロセス優先度を使用しません](../code-quality/ca1600.md)|プロセス優先順位に Idle を設定しないでください。 System.Diagnostics.ProcessPriorityClass.Idle を設定したプロセスは、CPU を占有するか、そうでない場合はアイドル状態になるため、スタンバイ状態がブロックされます。|
|[CA1601: 電源の状態の変更を妨げるタイマーを使用しません](../code-quality/ca1601.md)|定期的な動作の頻度が高くなると、CPU のビジー状態が続き、ディスプレイとハード ディスクをオフにする省電力アイドル タイマーに影響を与えます。|
