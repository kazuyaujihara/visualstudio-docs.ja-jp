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
- MSBuild (C++), MultiToolTask task
- MultiToolTask task (MSBuild (C++))
author: mikeblome
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: 137fb53a46c3fa31a69602906ef53d2f65e25c4b
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72747235"
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