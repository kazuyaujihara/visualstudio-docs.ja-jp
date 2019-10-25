---
title: オートメーションモデルを使用する |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], automation model
ms.assetid: 0c7f7889-fbfb-4b19-804f-b742138baecd
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4f1e1479232a684758359de7527f0c2fc9990cc7
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72722088"
---
# <a name="using-the-automation-model"></a>オートメーション モデルの使用
VSPackage を automation に接続した後、<xref:EnvDTE._DTE> オブジェクトで <xref:EnvDTE.DTEClass.GetObject%2A> メソッドを呼び出して、取得するオブジェクトを表す文字列を渡すことによって、プロパティとメソッドを取得できます。

## <a name="obtaining-project-objects"></a>取得 (プロジェクトオブジェクトを)
 次に、オートメーションコンシューマーがプロジェクトオートメーションオブジェクトを取得する方法を示す2つのコード例を示します。 DTE オブジェクトを取得する方法については、「[方法: dte オブジェクトと DTE2 オブジェクトへの参照を取得](https://msdn.microsoft.com/Library/c92e3c8e-82e6-4a67-85da-e43c50ffd8e4)する」を参照してください。

```vb
Sub DoAutomation()
    Dim MyProjects As Projects
    MyProjects = DTE.GetObject("AcmeProject")
End Sub
```

```cpp
void DoAutomation(void)
{
  CComQIPtr<Projects> pMyPkg; // Use an IDispatch-derived object type.
    pMyPkg = pDTE->GetObject("AcmeProjects");

   // The '=' performs a Query Interface.
   // Assumes pDTE is already available as a global.
   // Use pMyPkg to access your projects object's properties and methods.
}

```

 この時点で、特定の VSPackage の一部である標準のプロジェクトオブジェクトを使用して、階層モデルを下に移動できます。

 次のコード例は、カスタムプロジェクトの種類のプロパティであるカスタムオブジェクトを取得する方法を示しています。

```vb
Dim MyPrj As Project
Dim MyPrjItem As ProjectItem
Dim objMyObject as MyExtendedObject

MyPrj = MyProjects.Item(1) 'use the Projects collection to get a project
objMyObject = MyPrj.Object 'You call .Object to get to special Project
                           'implementation
objMyObject.MySpecialMethodOrProperty
```

 次のコードは、 **[ツール]** メニューの [[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 環境の**全般**] オプションにあるすべてのプロパティの名前を示しています。

```vb
dim objDTE
dim objEnv
set objDTE = CreateObject("VisualStudio.DTE")
set objEnv = objDTE.Properties("Environment", "General")
for each obj in ObjEnv
MsgBox obj.Name
Next

```

## <a name="see-also"></a>関連項目
- <xref:EnvDTE.DTEClass.GetObject%2A>