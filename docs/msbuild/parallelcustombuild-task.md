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
- MSBuild (Visual C++), ParallelCustomBuild task
- ParallelCustomBuild task (MSBuild (Visual C++))
author: mikeblome
ms.author: Michael.Blome
ms.workload:
- multiple
ms.openlocfilehash: 506ead6680bd9a0aaaf38d6959da02a14dfee337
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "58070405"
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