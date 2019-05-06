---
title: TASK_STATE_EXECUTED フィールド |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- TASK_STATE_EXECUTED field, Task class [.NET Framework debug engines]
ms.assetid: 75b8f9d0-b908-40d0-b109-70feaed2ab0c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7a822a47948df80c84ed6845590d5ec2a8c91ec6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62864338"
---
# <a name="taskstateexecuted-field"></a>TASK_STATE_EXECUTED field
タスクは実行中で、まだ完了していません。

 **名前空間:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **アセンブリ:** mscorlib (mscorlib.dll 内)

 .NET Framework からこの内部メンバーにアクセスできないため、次の構文には共通中間言語 (CIL) が提供されます。

## <a name="syntax"></a>構文

```csharp
.field static assembly literal int32 TASK_STATE_EXECUTED = int32(0x00020000)
```

## <a name="remarks"></a>Remarks
 場合、 [m_stateFlags](../../extensibility/debugger/m-stateflags-field.md)フィールドには、この値が含まれています、<xref:System.Threading.Tasks.Task.Status%2A>プロパティが返す<xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>します。

## <a name="see-also"></a>関連項目
- [Task クラス](../../extensibility/debugger/task-class-internal-members.md)