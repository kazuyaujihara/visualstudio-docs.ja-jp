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
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: a16a61c06bf80bef3fbb78f155cd8b41905a8d72
ms.sourcegitcommit: d78821f8c353e0102b1554719f549f32dffac71b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "58515182"
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