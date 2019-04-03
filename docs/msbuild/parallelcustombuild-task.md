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
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: 54623ab1c58d85de55c5b8a24384bf0be46f1a61
ms.sourcegitcommit: d78821f8c353e0102b1554719f549f32dffac71b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "58515127"
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