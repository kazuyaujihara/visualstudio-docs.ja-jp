---
title: CustomBuild タスク | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.custombuild
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), CustomBuild task
- CustomBuild task (MSBuild (Visual C++))
author: mikeblome
ms.author: Michael.Blome
ms.workload:
- multiple
ms.openlocfilehash: 183cdefbca29db486b84cb61f90501507e298838
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "58070411"
---
# <a name="custombuild-task"></a>CustomBuild タスク

Visual C++ コンパイラ ツール cmd.exe をラップします。

## <a name="parameters"></a>パラメーター

以下の表では、**CustomBuild** タスクのパラメーターについて説明します。

|パラメーター|説明|
|---------------|-----------------|
|**BuildSuffix**|省略可能な **string** 型のパラメーターです。|
|**Sources**|必須の **ITaskItem[]** 型のパラメーターです。|
|**TrackerLogDirectory**|省略可能な **string** 型のパラメーターです。|

## <a name="see-also"></a>関連項目

[タスク リファレンス](../msbuild/msbuild-task-reference.md)