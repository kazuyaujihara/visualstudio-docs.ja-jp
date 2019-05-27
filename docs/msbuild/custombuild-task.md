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
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: 6d466dec85a0bdf242120ef5e88a0d5f5d2ac48e
ms.sourcegitcommit: 0ef51e3517436a85cfb85bf492722d566ce602c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "65934506"
---
# <a name="custombuild-task"></a>CustomBuild タスク

Visual C++ コンパイラ ツール cmd.exe をラップします。 このクラスは [TrackedVCToolTask](../msbuild/trackedvctooltask-base-class.md) から派生しますが、ファイルの依存関係を見つける目的でファイル追跡が利用されることはありません。 インクリメント ビルドが正しく動作するには、依存関係をすべて AdditionalDependencies として明示的に指定する必要があります。


## <a name="parameters"></a>パラメーター

以下の表では、**CustomBuild** タスクのパラメーターについて説明します。

|パラメーター|説明|
|---------------|-----------------|
|**BuildSuffix**|省略可能な **string** 型のパラメーターです。|
|**Sources**|必須の **ITaskItem[]** 型のパラメーターです。|
|**TrackerLogDirectory**|省略可能な **string** 型のパラメーターです。|

## <a name="see-also"></a>関連項目

[タスク リファレンス](../msbuild/msbuild-task-reference.md)
