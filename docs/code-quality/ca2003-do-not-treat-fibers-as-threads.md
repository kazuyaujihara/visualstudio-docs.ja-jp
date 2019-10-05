---
title: CA2003:ファイバーをスレッドとして扱いません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2003
- DoNotTreatFibersAsThreads
helpviewer_keywords:
- CA2003
- DoNotTreatFibersAsThreads
ms.assetid: 15398fb1-f384-4bcc-ad93-00e1c0fa9ddf
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9f5e4e7eb28207cb37824b23acbbac02b6df380d
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233143"
---
# <a name="ca2003-do-not-treat-fibers-as-threads"></a>CA2003:ファイバーをスレッドとして扱いません

|||
|-|-|
|TypeName|DoNotTreatFibersAsThreads|
|CheckId|CA2003|
|カテゴリ|Microsoft.Reliability|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

マネージスレッドは Win32 スレッドとして扱われています。

## <a name="rule-description"></a>規則の説明

マネージスレッドが Win32 スレッドであると想定しないでください。ファイバーです。 共通言語ランタイム (CLR) は、SQL によって所有されている実際のスレッドのコンテキストで、マネージスレッドをファイバーとして実行します。 これらのスレッドは、SQL Server プロセス内の複数の Appdomain とデータベース間で共有できます。 マネージスレッドローカルストレージを使用することはできますが、アンマネージスレッドローカルストレージを使用したり、現在の OS スレッドでコードを再実行したりすることはできません。 スレッドのロケールなどの設定は変更しないでください。 P/Invoke を使用して CreateCriticalSection または Createmutex にを呼び出さないでください。そのためには、ロックを開始するスレッドもロックを終了する必要があります。 ファイバーを使用する場合、ロックに入るスレッドはロックを終了しないため、SQL では Win32 の重要なセクションとミューテックスは役に立ちません。 マネージスレッドローカルストレージや、スレッドの現在のユーザー <xref:System.Threading.Thread>インターフェイス (UI) カルチャなど、マネージオブジェクトのほとんどの状態を安全に使用できます。 ただし、プログラミングモデルの理由により、SQL の使用時にスレッドの現在のカルチャを変更することはできません。 この制限は、新しいアクセス許可によって適用されます。

## <a name="how-to-fix-violations"></a>違反の修正方法

スレッドの使用状況を確認し、それに応じてコードを変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則を抑制しないでください。