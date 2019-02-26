---
title: '方法: テンプレート内のパラメーターを置き換える |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- template parameters, substituting
- Visual Studio templates, using parameters
ms.assetid: a62924a7-4ba0-413d-b606-fdbe1fcf2807
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 97a8a99e160e4d488e44cc9e084789fe3a005eb1
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54780292"
---
# <a name="how-to-substitute-parameters-in-a-template"></a>方法 : テンプレート内のパラメーターを置き換える
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

テンプレートに基づいてファイルを作成するとき、クラス名や名前空間などのテンプレート パラメーターを置き換えることができます。 テンプレート パラメーターの完全な一覧については、「[テンプレート パラメーター](../ide/template-parameters.md)」をご覧ください。  
  
## <a name="procedure"></a>プロシージャ  
 テンプレートに基づいてプロジェクトを作成するときは常に、そのテンプレートのファイル内のパラメーターを置き換えることができます。 この手順では、テンプレートを使用して新しいプロジェクトを作成するとき、名前空間の名前を安全なプロジェクト名に置き換えるテンプレートの作成方法について説明します。  
  
#### <a name="to-use-a-parameter-to-replace-namespace-name-with-the-project-name"></a>パラメーターを使用して名前空間の名前をプロジェクト名に置き換えるには  
  
1.  テンプレートの 1 つ以上のコード ファイルにパラメーターを挿入します。 次に例を示します。  
  
    ```  
    namespace $safeprojectname$  
    ```  
  
    > [!NOTE]
    >  テンプレート パラメーターは、$*parameter*$ という形式で記述します。  
  
2.  テンプレートの .vstemplate ファイルで、このファイルを含む `ProjectItem` 要素を検索します。  
  
3.  `ProjectItem` 要素の `ReplaceParameters` 属性を `true` に設定します。 次に例を示します。  
  
    ```  
    <ProjectItem ReplaceParameters="true">Class1.cs</ProjectItem>  
    ```  
  
## <a name="see-also"></a>関連項目  
 [プロジェクトと項目テンプレートの作成](../ide/creating-project-and-item-templates.md)   
 [テンプレート パラメーター](../ide/template-parameters.md)   
 [Visual Studio テンプレート スキーマ参照](../extensibility/visual-studio-template-schema-reference.md)   
 [ProjectItem 要素 (Visual Studio 項目テンプレート)](../extensibility/projectitem-element-visual-studio-item-templates.md)
