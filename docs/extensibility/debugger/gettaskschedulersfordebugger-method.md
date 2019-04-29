---
title: GetTaskSchedulersForDebugger メソッド |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetTaskSchedulersForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 58aa236a-5ab8-4695-b303-89dffdbcd946
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d5df6dc3147a92f14d6858a82a6d997442dec30b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925655"
---
# <a name="gettaskschedulersfordebugger-method"></a>GetTaskSchedulersForDebugger メソッド
すべての配列を取得します<xref:System.Threading.Tasks.TaskScheduler>現在アクティブなオブジェクト。

 **名前空間:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **アセンブリ:** mscorlib (で*mscorlib.dll*)

 .NET Framework からこの内部メンバーにアクセスできないため、次の構文には共通中間言語 (CIL) が提供されます。

## <a name="syntax"></a>構文

```csharp
.method assembly hidebysig static class System.Threading.Tasks.TaskScheduler[] GetTaskSchedulersForDebugger() cil managed
```

## <a name="return-value"></a>戻り値
 すべての配列<xref:System.Threading.Tasks.TaskScheduler>これで現在アクティブなオブジェクト<xref:System.AppDomain>します。

## <a name="remarks"></a>Remarks
 このメソッドは、スレッド セーフであると同時の他のインスタンスを使用しないでください<xref:System.Threading.Tasks.TaskScheduler>します。 デバッガーがその他のすべてのスレッドを中断された場合にのみ、デバッガーからこのメソッドを呼び出します。

## <a name="see-also"></a>関連項目
- [TaskScheduler クラス](../../extensibility/debugger/taskscheduler-class-internal-members.md)