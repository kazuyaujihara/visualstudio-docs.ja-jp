---
title: CPPClean タスク | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- vc.task.cppclean
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), CPPClean task
- CPPClean task (MSBuild (Visual C++))
ms.assetid: b62a482e-8fb5-4999-b50b-6605a078e291
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e29a80c9cc3f492a19de630e2a09e1f15ca9c45c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54791440"
---
# <a name="cppclean-task"></a>CPPClean タスク
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]


Visual C++ プロジェクトのビルド時に MSBuild によって作成される一時ファイルを削除します。 ビルド ファイルを削除するプロセスは、*クリーニング* と呼ばれます。  

## <a name="parameters"></a>パラメーター  
 **CPPClean** タスクのパラメーターの説明を次の表に示します。  


|            パラメーター            |                                                                                                説明                                                                                                 |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        **DeletedFiles**         |                               省略可能な `ITaskItem[]` 型の出力パラメーターです。<br /><br /> タスクで使用および生成できる MSBuild 出力ファイル項目の配列を定義します。                                |
|          **DoDelete**           |                                                            省略可能な **Boolean** 型のパラメーターです。<br /><br /> `true` の場合は、一時ビルド ファイルを消去します。                                                             |
| **FilePatternsToDeleteOnClean** |                                            必須の `String` 型のパラメーターです。<br /><br /> 消去するファイルのファイル拡張子をセミコロンで区切ったリストを指定します。                                             |
|   **FilesExcludedFromClean**    |                                                    省略可能な `String` 型のパラメーターです。<br /><br /> 消去しないファイルをセミコロンで区切ったリストを指定します。                                                    |
|       **FoldersToClean**        | 必須の `String` 型のパラメーターです。<br /><br /> 消去するディレクトリをセミコロンで区切ったリストを指定します。 完全パスまたは相対パスを指定することができ、パスにはワイルドカード記号 (**\\**\*) を含めることができます。 |

## <a name="remarks"></a>解説  

## <a name="see-also"></a>関連項目
 [Task Reference (タスク リファレンス)](../msbuild/msbuild-task-reference.md)
