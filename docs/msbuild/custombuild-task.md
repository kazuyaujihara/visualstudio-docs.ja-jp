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
ms.openlocfilehash: 04f33f3852f051e1f492cb2b6dca44fcdb260e11
ms.sourcegitcommit: 32144a09ed46e7223ef7dcab647a9f73afa2dd55
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2019
ms.locfileid: "67587017"
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
