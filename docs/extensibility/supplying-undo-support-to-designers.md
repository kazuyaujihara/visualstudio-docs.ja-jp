---
title: デザイナー サポート提供元に戻す |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- designers [Visual Studio SDK], undo support
ms.assetid: 43eb1f14-b129-404a-8806-5bf9b099b67b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dc17f59858637048c12929411a0f413ed625ad10
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66331633"
---
# <a name="supply-undo-support-to-designers"></a>デザイナーに供給元に戻す機能

通常、デザイナー、エディターなどは、コード要素を変更するときに、ユーザーは、最近の変更を取り消すことができるように、元に戻す操作をサポートする必要があります。

Visual Studio で実装されたほとんどのデザイナーがある「取り消し」のサポートが、環境によって自動的に提供します。

元に戻す機能のサポートを提供する必要があるデザイナーの実装:

- 抽象基本クラスを実装して元に戻す管理を提供します。 <xref:System.ComponentModel.Design.UndoEngine>

- 実装によって永続化を指定し、CodeDOM のサポート、<xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService>と<xref:System.ComponentModel.Design.IComponentChangeService>クラス。

デザイナーを使用して記述の詳細については[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]を参照してください[デザイン時サポートの拡張](/previous-versions/37899azc(v=vs.140))します。

[!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)]によって既定の元に戻すインフラストラクチャを提供します。

- 管理の実装を提供する元に戻す、<xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine>と<xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine.UndoUnit>クラス。

- 永続性と既定のを通じて CodeDOM のサポートを提供する<xref:System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService>と<xref:System.ComponentModel.Design.IComponentChangeService>実装します。

## <a name="obtain-undo-support-automatically"></a>取り消しのサポートを自動的に取得します。

Visual Studio で作成されたすべてのデザイナーが自動および完全な取り消しのサポートの場合、デザイナー。

- 利用、<xref:System.Windows.Forms.Control>ベースのユーザー インターフェイスのクラス。

- コードの生成と永続化は、標準の CodeDOM に基づくコードの生成と解析システムを採用しています。

   Visual Studio の CodeDOM のサポートの使用方法の詳細については、次を参照してください。[動的ソース コードの生成とコンパイル](/dotnet/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation)します。

## <a name="when-to-use-explicit-designer-undo-support"></a>明示的なデザイナーの取り消しのサポートを使用する場合
 以外から提供されたいずれかのビューのアダプターと呼ばれる、グラフィカル ユーザー インターフェイスを使用している場合、デザイナーは、独自の元に戻す管理を指定する必要があります<xref:System.Windows.Forms.Control>します。

 この例は、web ベースのグラフィカル デザイン インターフェイスを備えた製品を作成可能性がありますがなく[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]-ベースのグラフィカル インターフェイスです。

 このような場合を使用して Visual Studio でこのビューのアダプターを登録する必要が 1 つは<xref:Microsoft.VisualStudio.Shell.Design.ProvideViewAdapterAttribute>、元に戻すの明示的な管理を提供します。

 デザイナーは、CodeDOM と永続化で提供される Visual Studio コード生成のモデルを使用しない場合のサポートを提供する必要があります、<xref:System.CodeDom>名前空間を作成します。

## <a name="undo-support-features-of-the-designer"></a>デザイナーのサポート機能を元に戻す
 環境の SDK には、提供するために必要なインターフェイスの既定の実装を使用していないデザイナーで使用できるサポートを元に戻す<xref:System.Windows.Forms.Control>ベースのユーザー インターフェイスや標準の CodeDOM と永続化モデルのクラス。

 <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine>クラスから派生、 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] <xref:System.ComponentModel.Design.UndoEngine>クラスの実装を使用して、<xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager>元に戻す操作を管理するクラス。

 Visual Studio には、デザイナーの元に戻すには、次の機能が用意されています。

- リンク元に戻す機能を複数のデザイナー。

- デザイナー内で子ユニットが実装することで親と対話できます<xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoUnit>と<xref:Microsoft.VisualStudio.OLE.Interop.IOleParentUndoUnit>で<xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine.UndoUnit>します。

環境の SDK では、CodeDOM と永続化を指定してサポートを提供します。

- <xref:System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService> 実装として、 <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService>

- A <xref:System.ComponentModel.Design.IComponentChangeService> Visual Studio のデザイン ホストによって提供されます。

## <a name="use-the-environment-sdk-features-to-supply-undo-support"></a>環境の SDK の機能を使用して、取り消しのサポートを提供するには

を取得する元に戻す機能、デザイナーを実装するオブジェクトする必要がありますをインスタンス化してのインスタンスを初期化、<xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine>有効なクラス<xref:System.IServiceProvider>実装します。 これは、<xref:System.IServiceProvider>クラスは、次のサービスを提供する必要があります。

- <xref:System.ComponentModel.Design.IDesignerHost>。

- <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService>

   Visual Studio の CodeDOM シリアル化を使用してデザイナーを使用することもできます<xref:System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService>で提供される、[!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)]の実装として、<xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService>します。

   ここで、<xref:System.IServiceProvider>クラスに提供される、<xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine>コンス トラクターの実装としてこのオブジェクトを返す必要があります、<xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService>クラス。

- <xref:System.ComponentModel.Design.IComponentChangeService>

   既定値を使用するデザイナー<xref:System.ComponentModel.Design.DesignSurface>の既定の実装を持つことによって Visual Studio のデザイン ホストが保証が提供される、<xref:System.ComponentModel.Design.IComponentChangeService>クラス。

デザイナーを実装する、<xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine>に基づいて元に戻すメカニズムは、場合に自動的に変更を追跡します。

- プロパティの変更がによる、<xref:System.ComponentModel.TypeDescriptor>オブジェクト。

- <xref:System.ComponentModel.Design.IComponentChangeService> イベントは、取り消し可能な変更がコミットされたときに手動で生成されます。

- コンテキスト内で作成された、デザイナーでの変更、<xref:System.ComponentModel.Design.DesignerTransaction>します。

- いずれかを使用して元に戻す単位の実装によって提供される標準的な取り消し単位を明示的に作成する、デザイナーで選択されます<xref:System.ComponentModel.Design.UndoEngine.UndoUnit>または Visual Studio に固有の実装<xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine.UndoUnit>から派生した<xref:System.ComponentModel.Design.UndoEngine.UndoUnit>も用意されていて、両方の実装<xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoUnit>と<xref:Microsoft.VisualStudio.OLE.Interop.IOleParentUndoUnit>します。

## <a name="see-also"></a>関連項目

- <xref:System.ComponentModel.Design.UndoEngine>
- <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine>
- [デザイン時サポートを拡張します。](/previous-versions/37899azc(v=vs.140))