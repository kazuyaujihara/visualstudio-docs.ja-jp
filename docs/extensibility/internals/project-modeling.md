---
title: プロジェクトモデリング |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], implementing project objects
- project models, automation
ms.assetid: c8db8fdb-88c1-4b12-86fe-f3c30a18f9ee
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 42e810a36478e49a578c6713d20f1bfc6be98309
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72725560"
---
# <a name="project-modeling"></a>プロジェクトのモデリング
プロジェクトの自動化を提供する次の手順は、標準のプロジェクトオブジェクト (<xref:EnvDTE.Projects> コレクションと `ProjectItems` コレクション) を実装することです。`Project` オブジェクトと <xref:EnvDTE.ProjectItem> オブジェクト。および残りのオブジェクトは、実装に固有です。 これらの標準オブジェクトは、Dteinternal .h ファイルで定義されています。 標準オブジェクトの実装は、BscPrj サンプルに用意されています。 これらのクラスをモデルとして使用して、他のプロジェクトの種類のプロジェクトオブジェクトとサイドバイサイドで実行する独自の標準プロジェクトオブジェクトを作成できます。

 オートメーションコンシューマーは、<xref:EnvDTE.Solution> ("`<UniqueProjName>")` と <xref:EnvDTE.ProjectItems> (`n`) を呼び出すことができることを前提としています。ここで、n は、ソリューション内の特定のプロジェクトを取得するためのインデックス番号です。 このオートメーション呼び出しを行うと、環境は適切なプロジェクト階層で <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.GetProperty%2A> を呼び出し、ItemID パラメーターと VSHPROPID_ExtObject を VSHPROPID パラメーターとして渡します。 `IVsHierarchy::GetProperty` は、実装したコア `Project` インターフェイスを提供するオートメーションオブジェクトへの `IDispatch` ポインターを返します。

 @No__t_0 の構文を次に示します。

 `HRESULT GetProperty (`

 `VSITEMID` `itemid`、

 `VSHPROPID` `propid`、

 `VARIANT` `*pvar`

 `);`

 プロジェクトは、入れ子にすることができ、コレクションを使用してプロジェクト項目のグループを作成します。 階層は次のようになります。

```
Projects
  |- Project
      |- ProjectItems (a collection of ProjectItem)
          |- ProjectItem (single object) or ProjectItems (another collection)
```

 入れ子とは、`ProjectItems` コレクションに入れ子になったオブジェクトを含めることができるため、<xref:EnvDTE.ProjectItem> オブジェクトを同時に <xref:EnvDTE.ProjectItems> コレクションにすることができることを意味します。 基本的なプロジェクトのサンプルでは、この入れ子については説明しません。 @No__t_0 オブジェクトを実装することによって、全体的なオートメーションモデルの設計を特徴とするツリーのような構造に関与します。

 プロジェクトオートメーションは、次の図のパスに従います。

 ![Visual Studio プロジェクトオブジェクト](../../extensibility/internals/media/projectobjects.gif "ProjectObjects")プロジェクトの自動化

 @No__t_0 オブジェクトを実装していない場合でも、プロジェクトの名前のみを含む汎用 `Project` オブジェクトが環境によって返されます。

## <a name="see-also"></a>関連項目
- <xref:EnvDTE.Projects>
- <xref:EnvDTE.ProjectItem>
- <xref:EnvDTE.ProjectItems>