---
title: TASK_STATE_FAULTED フィールド |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- TASK_STATE_FAULTED field, Task class [.NET Framework debug engines]
ms.assetid: ced826ae-09a9-4acf-af00-a2343d396bb8
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f8ae3c654518ec051d3f4d1fd0eeb43b4ef5e710
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66348361"
---
# <a name="taskstatefaulted-field"></a>TASK_STATE_FAULTED フィールド
タスクはハンドルされない例外が発生したために終了しました。

 **名前空間:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **アセンブリ:** mscorlib (で*mscorlib.dll*)

 .NET Framework からこの内部メンバーにアクセスできないため、次の構文には共通中間言語 (CIL) が提供されます。

## <a name="syntax"></a>構文

```csharp
.field static assembly literal int32 TASK_STATE_FAULTED = int32(0x00400000)
```

## <a name="remarks"></a>Remarks
 場合、 [m_stateFlags](../../extensibility/debugger/m-stateflags-field.md)フィールドには、この値が含まれています、<xref:System.Threading.Tasks.Task.Status%2A>プロパティが返す<xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>します。

## <a name="see-also"></a>関連項目
- [Task クラス](../../extensibility/debugger/task-class-internal-members.md)