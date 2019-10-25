---
title: Visual Studio 相互運用機能アセンブリの使用 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, interop assemblies
- interop assemblies, Visual Studio
- managed VSPackages, interop assemblies
ms.assetid: 1043eb95-4f0d-4861-be21-2a25395b3b3c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d0db6e0e0d5014f09a84316143af40f410bc1b10
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72722102"
---
# <a name="using-visual-studio-interop-assemblies"></a>Visual Studio 相互運用機能アセンブリの使用
Visual Studio 相互運用機能アセンブリを使用すると、マネージアプリケーションは Visual Studio の拡張機能を提供する COM インターフェイスにアクセスできます。 ストレート COM インターフェイスとその相互運用バージョンにはいくつかの違いがあります。 たとえば、Hresult は通常 int 値として表され、例外と同様に処理する必要があり、パラメーター (特に出力パラメーター) は異なる方法で処理する必要があります。

## <a name="handling-hresults-returned-to-managed-code-from-com"></a>COM からマネージド コードに返される HRESULT の処理
 マネージド コードから COM インターフェイスを呼び出す場合は、HRESULT 値を確認し、必要な場合に例外をスローします。 渡された HRESULT の値に応じて、<xref:Microsoft.VisualStudio.ErrorHandler> クラスには COM 例外をスローする <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> メソッドが含まれます。

 既定では、<xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> は、0 より小さい値を持つ HRESULT を渡されるたびに例外をスローします。 このような HRESULT が許容される値であり、例外をスローする必要がない場合は、値のテスト後に追加 HRESULT の値を <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> に渡す必要があります。 テスト対象の HRESULT が、<xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> に明示的に渡される HRESULT 値と一致する場合、例外はスローされません。

> [!NOTE]
> @No__t_0 クラスには、一般的な HRESULT の定数が含まれています。たとえば、<xref:Microsoft.VisualStudio.VSConstants.S_OK> や <xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL>、および <xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA> や <xref:Microsoft.VisualStudio.VSConstants.VS_E_UNSUPPORTEDFORMAT> などの HRESULT [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] です。 また、<xref:Microsoft.VisualStudio.VSConstants> には、COM の SUCCEEDED および FAILED マクロに対応する <xref:Microsoft.VisualStudio.ErrorHandler.Succeeded%2A> および <xref:Microsoft.VisualStudio.ErrorHandler.Failed%2A> メソッドが用意されています。

 たとえば、<xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL> が許容可能な戻り値であり、ゼロ未満の他の HRESULT がエラーを表す次の関数呼び出しがあるとします。

 [!code-vb[VSSDKHRESULTInformation#1](../../extensibility/internals/codesnippet/VisualBasic/using-visual-studio-interop-assemblies_1.vb)]
 [!code-csharp[VSSDKHRESULTInformation#1](../../extensibility/internals/codesnippet/CSharp/using-visual-studio-interop-assemblies_1.cs)]

 許容可能な戻り値が複数ある場合は、<xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> への呼び出しの一覧にのみ追加の HRESULT 値を追加することができます。

 [!code-vb[VSSDKHRESULTInformation#2](../../extensibility/internals/codesnippet/VisualBasic/using-visual-studio-interop-assemblies_2.vb)]
 [!code-csharp[VSSDKHRESULTInformation#2](../../extensibility/internals/codesnippet/CSharp/using-visual-studio-interop-assemblies_2.cs)]

## <a name="returning-hresults-to-com-from-managed-code"></a>マネージド コードから COM に HRESULT を返す
 例外が発生しない場合、マネージド コードは呼び出し元の COM 関数に <xref:Microsoft.VisualStudio.VSConstants.S_OK> を返します。 COM 相互運用では、マネージド コードで厳密に型指定される一般的な例外がサポートされます。 たとえば、受け入れられない `null` 引数を受け取るメソッドは、<xref:System.ArgumentNullException> をスローします。

 スローする例外が不明であり、COM に戻す HRESULT がわかっている場合は、<xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> メソッドを使用して、適切な例外をスローすることができます。 これは、<xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA> などの非標準のエラーでも機能します。 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> では、渡された HRESULT を厳密に型指定された例外にマップすることを試みます。 できない場合は、代わりに一般的な COM 例外をスローします。 最終的な結果では、マネージド コードから <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> に渡す HRESULT が呼び出し元の COM 関数に返されます。

> [!NOTE]
> 例外によって、パフォーマンスが低下します。例外は、異常なプログラムの条件を示すことを目的としています。 頻繁に発生する条件は、スローされた例外ではなく、インラインで処理をする必要があります。

## <a name="iunknown-parameters-passed-as-type-void"></a>型 void * * として渡された IUnknown パラメーター
 COM インターフェイスで `void **` 型として定義されているが、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 相互運用機能アセンブリメソッドプロトタイプで `[``iid_is``]` として定義されている [out] パラメーターを検索します。

 場合によっては、COM インターフェイスによって `IUnknown` オブジェクトが生成され、COM インターフェイスによって型 `void **` として渡されます。 これらのインターフェイスは、変数が IDL で [out] として定義されている場合、`IUnknown` オブジェクトは、`AddRef` メソッドを使用して参照カウントされるため、特に重要です。 オブジェクトが正しく処理されない場合、メモリリークが発生します。

> [!NOTE]
> COM インターフェイスによって作成され、[out] 変数で返された `IUnknown` オブジェクトは、明示的に解放されていない場合にメモリリークを発生させます。

 このようなオブジェクトを処理するマネージメソッドでは、<xref:System.IntPtr> を `IUnknown` オブジェクトへのポインターとして扱い、<xref:System.Runtime.InteropServices.Marshal.GetObjectForIUnknown%2A> メソッドを呼び出してオブジェクトを取得する必要があります。 その後、呼び出し元は、戻り値を適切な型にキャストする必要があります。 オブジェクトが不要になった場合は、<xref:System.Runtime.InteropServices.Marshal.Release%2A> を呼び出して解放します。

 @No__t_0 メソッドを呼び出し、`IUnknown` オブジェクトを正しく処理する例を次に示します。

```
MyClass myclass;
Object object;
IntPtr pObj;
Guid iid = Typeof(MyClass).Guid;
int hr = windowFrame.QueryViewInterface(ref iid, out pObj);
if (NativeMethods.Succeeded(hr))
{
    try
    {
        object = Marshal.GetObjectForIUnknown(pObj);
        myclass = object;
    }
    finally
    {
        Marshal.Release(pObj);
    }
}
else
{
    // error calling QueryViewInterface
}
```

> [!NOTE]
> 次のメソッドは、`IUnknown` オブジェクトポインターを型 <xref:System.IntPtr> として渡すことがわかっています。 このセクションで説明されているように処理します。

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A>

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.InitializeForOwner%2A>

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetNestedHierarchy%2A>

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.CreateProject%2A>

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.QueryViewInterface%2A>

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2.get_CfgType%2A>

## <a name="optional-out-parameters"></a>省略可能な [out] パラメーター
 COM インターフェイスで [out] データ型 (`int`、`object` など) として定義されているが、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 相互運用機能アセンブリメソッドプロトタイプで同じデータ型の配列として定義されているパラメーターを探します。

 @No__t_0 などの一部の COM インターフェイスでは、[out] パラメーターは省略可能として扱われます。 オブジェクトが不要な場合、これらの COM インターフェイスは、[out] オブジェクトを作成するのではなく、そのパラメーターの値として `null` ポインターを返します。 これは仕様に基づく制限事項です。 これらのインターフェイスの場合、`null` ポインターは VSPackage の正しい動作の一部と見なされ、エラーは返されません。

 CLR では [out] パラメーターの値を `null` できないため、これらのインターフェイスのデザインされた動作の一部は、マネージコード内で直接使用することはできません。 影響を受けるインターフェイスの相互運用機能アセンブリメソッド [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] は、CLR が `null` 配列を渡すことができるため、関連するパラメーターを配列として定義することで問題を回避できます。

 これらのメソッドのマネージ実装は、返されるものがない場合に、パラメーターに `null` 配列を配置する必要があります。 それ以外の場合は、正しい型の1つの要素から成る配列を作成し、戻り値を配列に格納します。

 省略可能な [out] パラメーターを使用してインターフェイスから情報を受け取るマネージメソッドは、パラメーターを配列として受け取ります。 配列の最初の要素の値を確認するだけです。 @No__t_0 ない場合は、最初の要素を元のパラメーターとして扱います。

## <a name="passing-constants-in-pointer-parameters"></a>ポインターパラメーターでの定数の引き渡し
 COM インターフェイスで [in] ポインターとして定義されているパラメーターを検索しますが、これは [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 相互運用機能アセンブリメソッドプロトタイプの <xref:System.IntPtr> 型として定義されています。

 同様の問題は、COM インターフェイスがオブジェクトポインターではなく、0、-1、または-2 などの特別な値を渡した場合にも発生します。 @No__t_0 とは異なり、CLR では、定数をオブジェクトとしてキャストすることはできません。 代わりに、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 相互運用機能アセンブリが <xref:System.IntPtr> 型としてパラメーターを定義します。

 これらのメソッドのマネージ実装では、必要に応じて、オブジェクトまたは整数定数から <xref:System.IntPtr> を作成するために、<xref:System.IntPtr> クラスに `int` と `void *` の両方のコンストラクターがあるという事実を活用する必要があります。

 この型の <xref:System.IntPtr> パラメーターを受け取るマネージメソッドでは、<xref:System.IntPtr> 型変換演算子を使用して結果を処理する必要があります。 まず、<xref:System.IntPtr> を `int` に変換し、関連する整数定数に対してテストします。 一致する値がない場合は、必要な型のオブジェクトに変換して続行します。

 この例については、「<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>」および「<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenSpecificEditor%2A>」を参照してください。

## <a name="ole-return-values-passed-as-out-parameters"></a>[Out] パラメーターとして渡される OLE 戻り値
 COM インターフェイスに `retval` 戻り値を持ち、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 相互運用機能アセンブリメソッドプロトタイプに戻り値が `int`、追加の [out] 配列パラメーターを持つメソッドを検索します。 @No__t_0 相互運用機能アセンブリメソッドプロトタイプには COM インターフェイスメソッドよりも1つ多くのパラメーターがあるため、これらのメソッドでは特別な処理が必要であることを明確にする必要があります。

 OLE アクティビティを処理する多くの COM インターフェイスは、OLE ステータスに関する情報を、インターフェイスの `retval` 戻り値に格納されている呼び出し元のプログラムに送信します。 対応する [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 相互運用機能アセンブリメソッドは、戻り値を使用する代わりに、[out] 配列パラメーターに格納されている呼び出し元のプログラムに情報を送り返します。

 これらのメソッドのマネージ実装では、[out] パラメーターと同じ型の単一要素配列を作成し、パラメーターに配置する必要があります。 配列要素の値は、適切な COM `retval` と同じである必要があります。

 この型のインターフェイスを呼び出すマネージメソッドは、[out] 配列から最初の要素を取得する必要があります。 この要素は、対応する COM インターフェイスから `retval` の戻り値であるかのように処理できます。

## <a name="see-also"></a>関連項目
- [アンマネージ コードとの相互運用](/dotnet/framework/interop/index)