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
- MSBuild (C++), CustomBuild task
- CustomBuild task (MSBuild (C++))
author: mikeblome
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: 678068d1b6acc055fa65e6d0305b07152ed28695
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72748113"
---
# <a name="custombuild-task"></a>CustomBuild タスク

Microsoft C++ コンパイラ ツール cmd.exe をラップします。 このクラスは [TrackedVCToolTask](../msbuild/trackedvctooltask-base-class.md) から派生しますが、ファイルの依存関係を見つける目的でファイル追跡が利用されることはありません。 インクリメント ビルドが正しく動作するには、依存関係をすべて AdditionalDependencies として明示的に指定する必要があります。

## <a name="parameters"></a>パラメーター

以下の表では、**CustomBuild** タスクのパラメーターについて説明します。

|パラメーター|説明|
|---------------|-----------------|
|**BuildSuffix**|省略可能な **string** 型のパラメーターです。|
|**Sources**|必須の **ITaskItem[]** 型のパラメーターです。|
|**TrackerLogDirectory**|省略可能な **string** 型のパラメーターです。|

## <a name="see-also"></a>関連項目

[タスク リファレンス](../msbuild/msbuild-task-reference.md)
