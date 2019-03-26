---
title: VCToolTask クラス | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
author: mikeblome
ms.author: Michael.Blome
ms.workload:
- multiple
ms.openlocfilehash: 4c7cc3490735dbd9ac43cd43555ec673cc3afccd
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "58070445"
---
# <a name="vctooltask-base-class"></a>VCToolTask 基底クラス

多くのタスクは最終的に <xref:Microsoft.Build.Utilities.Task> クラスおよび [ToolTask](/dotnet/api/microsoft.build.utilities.tooltask) クラスから継承します。 このクラスは、それから派生するタスクにいくつかのパラメーターを追加します。 このドキュメントでは、これらのパラメーターを示します。

## <a name="parameters"></a>パラメーター

以下の表では、**VCToolTask** 基底クラスのパラメーターについて説明します。

|パラメーター|説明|
|---------------|-----------------|
|**ActiveToolSwitchesValues**|省略可能な **Dictionary\<string, ToolSwitch>** のパラメーターです。|
|**AdditionalOptions**|省略可能な **string** 型のパラメーターです。|
|**EffectiveWorkingDirectory**|省略可能な **string** 型のパラメーターです。|
|**EnableErrorListRegex**|省略可能な **bool** 型のパラメーターです。<br/><br/>既定値は `true` です。|
|**ErrorListRegex**|省略可能な **ITaskItem[]** パラメーターです。|
|**ErrorListListExclusion**|省略可能な **ITaskItem[]** パラメーターです。|
|**GenerateCommandLine**|省略可能な **string** 型のパラメーターです。<br/><br/>値 **CommandLineFormat** *format* [default = CommandLineFormat.ForBuildLog] および **EscapeFormat** *escapeFormat* [default = EscapeFormat.Default] を使用します。|
|**GenerateCommandLineExceptSwitches**|省略可能な **string** 型のパラメーターです。<br/><br/>値 **string[]** *switchesToRemove*, **CommandLineFormat** *format* [default = CommandLineFormat.ForBuildLog], および **EscapeFormat** *escapeFormat* [default = EscapeFormat.Default] を使用します。|

## <a name="see-also"></a>関連項目

[タスク リファレンス](../msbuild/msbuild-task-reference.md)<br/>
[タスク](../msbuild/msbuild-tasks.md)