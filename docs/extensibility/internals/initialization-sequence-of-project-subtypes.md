---
title: プロジェクトのサブタイプの初期化シーケンス |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project subtypes, initialization sequence
ms.assetid: f657f8c3-5e68-4308-9971-e81e3099ba29
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 678f704c73a39cdf2130d36fcfb1a74925dd89d1
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72726877"
---
# <a name="initialization-sequence-of-project-subtypes"></a>プロジェクト サブタイプの初期化シーケンス
環境では、<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A> の基本プロジェクトファクトリの実装を呼び出すことによって、プロジェクトを構築します。 プロジェクトのサブタイプの構造は、プロジェクトファイルの拡張子に対するプロジェクトの種類の GUID リストが空でないと判断したときに開始されます。 プロジェクトファイルの拡張子とプロジェクト GUID によって、プロジェクトの種類が [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] であるか [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] であるかが指定されます。 たとえば、.vbproj 拡張子と {F184B08F-C81C-45F6-A57F-5ABD9991F28F} は、[!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] プロジェクトを識別します。

## <a name="environments-initialization-of-project-subtypes"></a>環境におけるプロジェクトのサブタイプの初期化
 次の手順では、複数のプロジェクトサブタイプによって集計されたプロジェクトシステムの初期化シーケンスについて詳しく説明します。

1. 環境は基本プロジェクトの <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A> を呼び出し、プロジェクトがプロジェクトファイルを解析している間に、[プロジェクトの種類の集計] の一覧が `null` ていないことを検出します。 プロジェクトはプロジェクトの直接作成を中止します。

2. プロジェクトは <xref:Microsoft.VisualStudio.Shell.Interop.SVsCreateAggregateProject> サービスで `QueryService` を呼び出して、<xref:Microsoft.VisualStudio.Shell.Interop.IVsCreateAggregateProject.CreateAggregateProject%2A> メソッドの環境の実装を使用してプロジェクトのサブタイプを作成します。 このメソッド内では、環境は <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A>、<xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.SetInnerProject%2A>、および <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.InitializeForOuter%2A> メソッドの実装に対して、最も外側のプロジェクトのサブタイプから始まるプロジェクトの種類の Guid の一覧を調べながら、再帰的な関数呼び出しを行います。

     次に、初期化の手順の詳細を示します。

    1. 環境の <xref:Microsoft.VisualStudio.Shell.Interop.IVsCreateAggregateProject.CreateAggregateProject%2A> メソッドの実装は、次の関数宣言を使用して `HrCreateInnerProj` メソッドを呼び出します。

         \<CodeContentPlaceHolder > 0 </CodeContentPlaceHolder>

         この関数が初めて呼び出されるとき、つまり、最も外側のプロジェクトのサブタイプでは、パラメーター `pOuter` と `pOwner` が `null` として渡され、関数は最も外側のプロジェクトのサブタイプ `IUnknown` を `pOuter` に設定します。

    2. 次に、環境は、リスト内の2番目のプロジェクトの種類の GUID を使用して `HrCreateInnerProj` 関数を呼び出します。 この GUID は、集計シーケンスの基本プロジェクトにステップインする2番目の内部プロジェクトサブタイプに対応します。

    3. @No__t_0 は、最も外側のプロジェクトのサブタイプの `IUnknown` を指し、`HrCreateInnerProj` <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A> の実装を呼び出した後、<xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.SetInnerProject%2A> の実装を呼び出すことができます。 @No__t_0 メソッドで、最も外側のプロジェクトのサブタイプの制御 `IUnknown` を渡します。 `pOuter` します。 所有されているプロジェクト (内部プロジェクトのサブタイプ) は、ここで集計プロジェクトオブジェクトを作成する必要があります。 @No__t_0 メソッドの実装では、集計される内部プロジェクトの `IUnknown` へのポインターを渡します。 これらの2つのメソッドは、集計オブジェクトを作成します。実装では、プロジェクトのサブタイプがそれ自体に参照カウントを保持しないようにするために、COM 集計規則に従う必要があります。

    4. `HrCreateInnerProj` は <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A> の実装を呼び出します。 このメソッドでは、プロジェクトのサブタイプは初期化に使用されます。 たとえば、<xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.InitializeForOuter%2A> にソリューションイベントを登録できます。

    5. `HrCreateInnerProj` は、リスト内の最後の GUID (基本プロジェクト) に到達するまで再帰的に呼び出されます。 これらの各呼び出しについて、c から d までの手順が繰り返されます。 `pOuter` は、集計レベルごとに、最も外側のプロジェクトサブタイプ `IUnknown` を指します。

## <a name="example"></a>例

次の例では、環境によって実装される、<xref:Microsoft.VisualStudio.Shell.Interop.IVsCreateAggregateProject.CreateAggregateProject%2A> メソッドのおおよその表現でのプログラムプロセスの詳細について説明します。 コードはほんの一例です。これはコンパイルするためのものではなく、わかりやすくするためにすべてのエラーチェックが削除されました。

```cpp
HRESULT CreateAggregateProject
(
    LPCOLESTR lpstrGuids,
    LPCOLESTR pszFilename,
    LPCOLESTR pszLocation,
    LPCOLESTR pszName,
    VSCREATEPROJFLAGS grfCreateFlags,
    REFIID iidProject,
    void **ppvProject)
{
    HRESULT hr = NOERROR;
    CComPtr<IUnknown> srpunkProj;
    CComPtr<IVsAggregatableProject> srpAggProject;
    CComBSTR bstrGuids = lpstrGuids;
    BOOL fCanceled = FALSE;
    *ppvProject = NULL;

    HrCreateInnerProj(
         bstrGuids, NULL, NULL, pszFilename, pszLocation,
         pszName, grfCreateFlags, &srpunkProj, &fCanceled);
    srpunkProj->QueryInterface(
        IID_IVsAggregatableProject, (void **)&srpAggProject));
    srpAggProject->OnAggregationComplete();
    srpunkProj->QueryInterface(iidProject, ppvProject);
}

HRESULT HrCreateInnerProj
(
    WCHAR *pwszGuids,
    IUnknown *pOuter,
    IVsAggregatableProject *pOwner,
    LPCOLESTR pszFilename,
    LPCOLESTR pszLocation,
    LPCOLESTR pszName,
    VSCREATEPROJFLAGS grfCreateFlags,
    IUnknown **ppInner,
    BOOL *pfCanceled
)
{
    HRESULT hr = NOERROR;
    CComPtr<IUnknown> srpInner;
    CComPtr<IVsAggregatableProject> srpAggInner;
    CComPtr<IVsProjectFactory> srpProjectFactory;
    CComPtr<IVsAggregatableProjectFactory> srpAggPF;
    GUID guid = GUID_NULL;
    WCHAR *pwszNextGuids = wcschr(pwszGuids, L';');
    WCHAR wszText[_MAX_PATH+150] = L"";

    if (pwszNextGuids)
    {
        *pwszNextGuids++ = 0;
    }

    CLSIDFromString(pwszGuids, &guid);
    GetProjectTypeMgr()->HrGetProjectFactoryOfGuid(
        guid, &srpProjectFactory);
    srpProjectFactory->QueryInterface(
        IID_IVsAggregatableProjectFactory,
        (void **)&srpAggPF);
    srpAggPF->PreCreateForOuter(pOuter, &srpInner);
    srpInner->QueryInterface(
        IID_IVsAggregatableProject, (void **)&srpAggInner);

    if (pOwner)
    {
        IfFailGo(pOwner->SetInnerProject(srpInner));
    }

    if (pwszNextGuids)
    {
        CComPtr<IUnknown> srpNextInner;
        HrCreateInnerProj(
            pwszNextGuids, pOuter ? pOuter : srpInner,
            srpAggInner, pszFilename, pszLocation, pszName,
            grfCreateFlags, &srpNextInner, pfCanceled);
    }

    return srpAggInner->InitializeForOuter(
        pszFilename, pszLocation, pszName, grfCreateFlags,
        IID_IUnknown, (void **)ppInner, pfCanceled);
}
```

## <a name="see-also"></a>関連項目

- <xref:Microsoft.VisualStudio.Shell.Flavor>
- [プロジェクト サブタイプ](../../extensibility/internals/project-subtypes.md)