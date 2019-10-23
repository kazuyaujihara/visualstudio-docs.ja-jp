---
title: ParallelCustomBuild タスク | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.parallelcustombuild
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (C++), ParallelCustomBuild task
- ParallelCustomBuild task (MSBuild (C++))
author: mikeblome
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: c6ea14e61eb2d62f3fc9ccdac3a17010ccc9194f
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72747217"
---
# <a name="parallelcustombuild-task"></a>ParallelCustomBuild タスク

[CustomBuild タスク](../msbuild/custombuild-task.md)の並列インスタンスを実行します。

## <a name="parameters"></a>パラメーター

以下の表では **ParallelCustomBuild** タスクのパラメーターについて説明します。

|パラメーター|説明|
|---------------|-----------------|
|**BreakOnFirstFailure**|省略可能な **bool** 型のパラメーターです。|
|**MaxItemsInBatch**|省略可能な **int** 型のパラメーターです。|
|**MaxProcesses**|省略可能な **int** 型のパラメーターです。|
|**Sources**|必須の **ITaskItem[]** 型のパラメーターです。|

## <a name="see-also"></a>関連項目

[タスク リファレンス](../msbuild/msbuild-task-reference.md)