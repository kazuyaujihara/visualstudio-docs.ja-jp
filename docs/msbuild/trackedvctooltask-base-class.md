---
title: TrackedVCToolTask クラス | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
author: mikeblome
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: 4a4044416131a27ca313d10d02404094c5f5e219
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62938870"
---
# <a name="trackedvctooltask-base-class"></a>TrackedVCToolTask 基底クラス

多くのタスクは最終的に <xref:Microsoft.Build.Utilities.Task> クラスおよび [ToolTask](/dotnet/api/microsoft.build.utilities.tooltask) クラスから継承します。 このクラスでは、[VCToolTask](../msbuild/vctooltask-base-class.md) から派生するタスクに複数のパラメーターが追加されます。 このドキュメントでは、これらのパラメーターを示します。

## <a name="parameters"></a>パラメーター

以下の表では、**TrackedVCToolTask** 基底クラスのパラメーターについて説明します。

|パラメーター|説明|
|---------------|-----------------|
|**DeleteOutputOnExecute**|省略可能な **bool** 型のパラメーターです。|
|**EnableExecuteTool**|省略可能な **bool** 型のパラメーターです。|
|**ExcludedInputPaths**|省略可能な **ITaskItem[]** パラメーターです。|
|**MinimalRebuildFromTracking**|省略可能な **bool** 型のパラメーターです。|
|**PathOverride**|省略可能な **string** 型のパラメーターです。|
|**PostBuildTrackingCleanup**|省略可能な **bool** 型のパラメーターです。|
|**RootSource**|省略可能な **string** 型のパラメーターです。|
|**SkippedExecution**|省略可能な **bool** 型の出力パラメーターです。|
|**SourcesCompiled**|省略可能な **ITaskItem[]** 型の出力パラメーターです。|
|**TLogCommandFile**|省略可能な **ITaskItem** 型のパラメーターです。|
|**TLogReadFiles**|省略可能な **ITaskItem[]** パラメーターです。|
|**TLogWriteFiles**|省略可能な **ITaskItem[]** パラメーターです。|
|**ToolArchitecture**|省略可能な **string** 型のパラメーターです。|
|**TrackCommandLines**|省略可能な **bool** 型のパラメーターです。|
|**TrackFileAccess**|省略可能な **bool** 型のパラメーターです。|
|**TrackedInputFilesToIgnore**|省略可能な **ITaskItem[]** パラメーターです。|
|**TrackedOutputFilesToIgnore**|省略可能な **ITaskItem[]** パラメーターです。|
|**TrackerFrameworkPath**|省略可能な **string** 型のパラメーターです。|
|**TrackerSdkPath**|省略可能な **string** 型のパラメーターです。|

## <a name="see-also"></a>関連項目

[タスク リファレンス](../msbuild/msbuild-task-reference.md)<br/>
[タスク](../msbuild/msbuild-tasks.md)