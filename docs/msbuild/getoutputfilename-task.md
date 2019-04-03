---
title: GetOutputFileName タスク | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.getoutputfilename
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), GetOutputFileName task
- GetOutputFileName task (MSBuild (Visual C++))
author: mikeblome
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: c6298a512a1848622bf854d6d9ee9084309a0b4f
ms.sourcegitcommit: d78821f8c353e0102b1554719f549f32dffac71b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "58514977"
---
# <a name="getoutputfilename-task"></a>GetOutputFileName タスク

cl や他のツールの出力ファイル名を取得するヘルパー タスクです。これにより、出力ディレクトリのみを指定する、完全なファイル名を指定する、または何も指定しないことが可能になります。

## <a name="parameters"></a>パラメーター

以下の表では、**GetOutputFileName** タスクのパラメーターについて説明します。

|パラメーター|説明|
|---------------|-----------------|
|**OutputExtension**|必須の **String** 型のパラメーターです。|
|**OutputFile**|省略可能な **string** 型の出力パラメーターです。|
|**OutputPath**|省略可能な **string** 型のパラメーターです。|
|**SourceFile**|必須の **String** 型のパラメーターです。|

## <a name="see-also"></a>関連項目

[タスク リファレンス](../msbuild/msbuild-task-reference.md)