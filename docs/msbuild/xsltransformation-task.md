---
title: XslTransformation タスク | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, XslTransformation task
- XslTransformation task [MSBuild]
ms.assetid: 6f3a7d81-3ae3-4703-9a06-870b32b69d80
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8330cb006143244458c9da0f3e76060275607fa5
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56617952"
---
# <a name="xsltransformation-task"></a>XslTransformation タスク
XSLT またはコンパイルされた XSLT を利用して XML 入力を変換し、出力デバイスまたはファイルに出力します。

## <a name="parameters"></a>パラメーター
 `XslTransformation` タスクのパラメーターの説明を次の表に示します。

|パラメーター|説明|
|---------------|-----------------|
|`OutputPaths`|必須の <xref:Microsoft.Build.Framework.ITaskItem>`[]` 型のパラメーターです。<br /><br /> XML 変換の出力ファイルを指定します。|
|`Parameters`|省略可能な `String` 型のパラメーターです。<br /><br /> XSLT 入力ドキュメントにパラメーターを指定します。|
|`XmlContent`|省略可能な `String` 型のパラメーターです。<br /><br /> XML 入力を文字列として指定します。|
|`XmlInputPaths`|省略可能な <xref:Microsoft.Build.Framework.ITaskItem>`[]` 型のパラメーターです。<br /><br /> XML 入力ファイルを指定します。|
|`XslCompiledDllPath`|省略可能な <xref:Microsoft.Build.Framework.ITaskItem> 型のパラメーターです。<br /><br /> コンパイルされた XSLT を指定します。|
|`XslContent`|省略可能な `String` 型のパラメーターです。<br /><br /> XSLT 入力を文字列として指定します。|
|`XslInputPath`|省略可能な <xref:Microsoft.Build.Framework.ITaskItem> 型のパラメーターです。<br /><br /> XSLT 入力ファイルを指定します。|

## <a name="remarks"></a>解説
 表に示されているパラメーターを使用できるだけでなく、このタスクは <xref:Microsoft.Build.Tasks.TaskExtension> クラスからパラメーターを継承します。このクラス自体は <xref:Microsoft.Build.Utilities.Task> クラスから継承されます。 これらの追加のパラメーターの一覧とその説明については、「[TaskExtension Base Class](../msbuild/taskextension-base-class.md)」を参照してください。

## <a name="see-also"></a>関連項目
- [タスク](../msbuild/msbuild-tasks.md)
- [タスク リファレンス](../msbuild/msbuild-task-reference.md)