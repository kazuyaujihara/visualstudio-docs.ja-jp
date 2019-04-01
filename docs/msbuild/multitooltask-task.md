---
title: MultiToolTask タスク | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.multitooltask
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), MultiToolTask task
- MultiToolTask task (MSBuild (Visual C++))
author: mikeblome
ms.author: Michael.Blome
ms.workload:
- multiple
ms.openlocfilehash: bd0c5510c754043a0a55b305c671ce9487cabb49
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "58070432"
---
# <a name="multitooltask-task"></a>MultiToolTask タスク

説明はありません。

## <a name="parameters"></a>パラメーター

以下の表では、**MultiToolTask** タスクのパラメーターについて説明します。

|パラメーター|説明|
|---------------|-----------------|
|**EnvironmentVariablesToSet**|省略可能な **string[]** 型のパラメーターです。|
|**SemaphoreProcCount**|省略可能な **string** 型のパラメーターです。|
|**SchedulerFunction**|省略可能な **string** 型のパラメーターです。|
|**SchedulerVerbose**|省略可能な **bool** 型のパラメーターです。|
|**Sources**|必須の **ITaskItem[]** 型のパラメーターです。|
|**TaskAssemblyName**|省略可能な **string** 型のパラメーターです。|
|**TaskName**|必須の **String** 型のパラメーターです。|
|**TrackerLogDirectory**|必須の **String** 型のパラメーターです。|

## <a name="see-also"></a>関連項目

[タスク リファレンス](../msbuild/msbuild-task-reference.md)