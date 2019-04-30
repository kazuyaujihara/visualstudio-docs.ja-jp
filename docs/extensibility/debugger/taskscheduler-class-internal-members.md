---
title: TaskScheduler クラスの内部メンバー |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- TaskScheduler class [.NET Framework debug engines]
- debug engines, TaskScheduler class [.NET Framework]
ms.assetid: 87f1c969-0217-4464-8907-7609c1bf61d3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cf7b693c058cd69ab2dcb79be787cf5a16d8f8a0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62864024"
---
# <a name="taskscheduler-class---internal-members"></a>TaskScheduler クラスの内部メンバー
この記事の内部メンバーを説明します、<xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>する際に役立つクラスがカスタムのデバッガーを実装します。 このクラスの詳細については、次を参照してください。、<xref:System.Threading.Tasks.TaskScheduler>参照資料です。

 **名前空間:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **アセンブリ:** mscorlib (で*mscorlib.dll*)

 .NET Framework からこれらの内部メンバーにアクセスできないため、次の構文には共通中間言語 (CIL) が提供されます。

## <a name="syntax"></a>構文

```csharp
.class public abstract auto ansi beforefieldinit System.Threading.Tasks.TaskScheduler
       extends System.Object
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|名前|説明|
|----------|-----------------|
|[GetScheduledTasksForDebugger](../../extensibility/debugger/getscheduledtasksfordebugger-method.md)|すべてのスケジュールされたタスクの配列を取得します。|
|[GetTaskSchedulersForDebugger](../../extensibility/debugger/gettaskschedulersfordebugger-method.md)|すべての配列を取得します<xref:System.Threading.Tasks.TaskScheduler>現在アクティブなオブジェクト。|

## <a name="remarks"></a>Remarks

## <a name="see-also"></a>関連項目
- <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>
- [.NET Framework の並列拡張機能の内部](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)