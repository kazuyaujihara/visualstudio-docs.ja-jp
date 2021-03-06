---
title: CreateProperty タスク | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#CreateProperty
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CreateProperty task [MSBuild]
- MSBuild, CreateProperty task
ms.assetid: fbc31a88-62d4-43d2-b739-68ef3fac38f5
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3c18288e5088871703605da4915786486e2e864b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49267658"
---
# <a name="createproperty-task"></a>CreateProperty タスク
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
渡された値をプロパティに入力します。 プロパティ間または文字列間で値をコピーできます。  
  
## <a name="attributes"></a>属性  
 `CreateProperty` タスクのパラメーターの説明を次の表に示します。  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Value`|省略可能な `String` 型の出力パラメーターです。<br /><br /> 新しいプロパティにコピーする値を指定します。|  
|`ValueSetByTask`|省略可能な `String` 型の出力パラメーターです。<br /><br /> `Value` パラメーターと同じ値を含みます。 出力が最新の状態であるため、含まれているターゲットをスキップするとき、[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] によって出力プロパティが設定されることを回避する場合にのみ、このパラメーターを使用します。|  
  
## <a name="remarks"></a>Remarks  
 上記のパラメーター以外に、このタスクは <xref:Microsoft.Build.Tasks.TaskExtension> クラスからパラメーターを継承します。このクラス自体は、<xref:Microsoft.Build.Utilities.Task> クラスから継承されます。 これらの追加のパラメーターの一覧とその説明については、「 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、`CreateProperty` タスクによって `NewFile` プロパティが作成されます。`SourceFilename` および `SourceFileExtension` プロパティの値の組み合わせが使用されます。  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <PropertyGroup>  
        <SourceFilename>Module1</SourceFilename>  
        <SourceFileExtension>vb</SourceFileExtension>  
    </PropertyGroup>  
  
    <Target Name="CreateProperties">  
  
        <CreateProperty  
            Value="$(SourceFilename).$(SourceFileExtension)">  
            <Output  
                TaskParameter="Value"  
                PropertyName="NewFile" />  
        </CreateProperty>  
  
    </Target>  
  
</Project>  
```  
  
 プロジェクトの実行後、`NewFile` プロパティの値は `Module1.vb` になります。  
  
## <a name="see-also"></a>関連項目  
 [Task Reference (タスク リファレンス)](../msbuild/msbuild-task-reference.md)   
 [タスク](../msbuild/msbuild-tasks.md)



