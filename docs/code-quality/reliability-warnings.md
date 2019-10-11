---
title: 信頼性に関する警告
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.reliabilityrules
helpviewer_keywords:
- warnings, reliability
- reliability warnings
- managed code analysis warnings, reliability warnings
ms.assetid: 77886846-10a2-4585-968a-7eb60ebe07e8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cb39bb5f59373f52d77c7cc5d13d12544d4c0314
ms.sourcegitcommit: 3e94d9fb6dc56fa8b23fbacd5d11cf8d6e7e18f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "72252592"
---
# <a name="reliability-warnings"></a>信頼性に関する警告

信頼性の警告は、正しいメモリやスレッドの使用など、ライブラリとアプリケーションの信頼性をサポートします。 信頼性の規則は次のとおりです。

|Rule|説明|
|----------|-----------------|
|[CA2000:スコープを失う前にオブジェクトを破棄する @ no__t-0|例外的なイベントが発生するとオブジェクトのファイナライザーを実行できないため、オブジェクトに対するすべての参照がスコープ外になる前に、オブジェクトを明示的に破棄する必要があります。|
|[CA2001:問題のあるメソッドを呼び出さないでください。 @ no__t-0|メンバーが危険性または問題のあるメソッドを呼び出します。|
|[CA2002:弱い id @ no__t を持つオブジェクトをロックしないでください。|アプリケーション ドメインの境界を越えてオブジェクトに直接アクセスできる場合、そのオブジェクトの ID は不十分と表現されます。 スレッドで ID が不十分なオブジェクトをロックしようとすると、ブロックされることがあります。たとえば、異なるアプリケーション ドメインの別スレッドで、既に同じオブジェクトがロックされている場合です。|
|[CA2003:ファイバーをスレッドとして扱いません @ no__t-0|マネージスレッドは Win32 スレッドとして扱われています。|
|[CA2004:GC の呼び出しを削除します。KeepAlive @ no__t-0|SafeHandle の使用法に変換する場合は、GC のすべての呼び出しを削除します。KeepAlive (オブジェクト)。 この場合、クラスは GC を呼び出す必要がありません。KeepAlive。ファイナライザーがなくても、SafeHandle に依存してそれらの OS ハンドルを最終処理することを前提としています。|
|[CA2006:SafeHandle を使用してネイティブリソースをカプセル化する @ no__t-0|マネージド コードで IntPtr を使用すると、セキュリティ上の問題および信頼性の問題が発生する可能性があります。 すべての IntPtr の使用状況をチェックして、SafeHandle または類似のテクノロジに置き換える必要があるかどうかを判断してください。|
|[CA2007:タスク @ no__t を直接待機しないでください。|非同期メソッドは、を<xref:System.Threading.Tasks.Task>直接[待機](/dotnet/csharp/language-reference/keywords/await)します。|
