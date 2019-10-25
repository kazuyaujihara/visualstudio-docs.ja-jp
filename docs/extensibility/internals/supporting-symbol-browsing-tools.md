---
title: シンボル参照ツールのサポート |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- symbols, symbol-browsing tools
- browsers, symbol browsers
- symbol-browsing tools
- libraries
- IVsLibrary2 interface, symbol-browsing tools
- IVsSimpleLibrary2 interface, symbol-browsing tools
- symbol-browsing tools, library manager
- symbols
- libraries, symbol-browsing tools
ms.assetid: 70d8c9e5-4b0b-4a69-b3b3-90f36debe880
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ca171fa75adda3deef5b941852fc3e6c648c84c6
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72723081"
---
# <a name="supporting-symbol-browsing-tools"></a>シンボル参照ツールのサポート
**オブジェクトブラウザー**、**クラスビュー**、**呼び出しブラウザー**および**検索シンボル結果**ツールは、Visual Studio のシンボル参照機能を提供します。 これらのツールでは、シンボルの階層ツリービューが表示され、ツリー内のシンボル間の関係が表示されます。 シンボルは、さまざまなコンポーネントに含まれる名前空間、オブジェクト、クラス、クラスメンバー、およびその他の言語要素を表すことができます。 コンポーネントには、Visual Studio プロジェクト、外部 .NET Framework コンポーネント、および型 (.tlb) ライブラリが含まれます。 詳細については、「[コードの構造の表示](../../ide/viewing-the-structure-of-code.md)」を参照してください。

## <a name="symbol-browsing-libraries"></a>シンボル参照ライブラリ
 言語の実装者は、コンポーネント内のシンボルを追跡するライブラリを作成し、一連のインターフェイスを使用して Visual Studio オブジェクトマネージャーにシンボルの一覧を提供することにより、Visual Studio のシンボル参照機能を拡張できます。 ライブラリは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2> インターフェイスによって記述されます。 Visual Studio オブジェクトマネージャーは、ライブラリからデータを取得して整理することにより、シンボル参照ツールからの新しいデータの要求に応答します。 その後、要求されたデータを使用してツールを設定または更新します。 Visual Studio オブジェクトマネージャーへの参照を取得するには、<xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2>、<xref:Microsoft.VisualStudio.Shell.Interop.SVsObjectManager> サービス ID を `GetService` メソッドに渡します。

 各ライブラリは、すべてのライブラリの情報を収集する Visual Studio オブジェクトマネージャーに登録する必要があります。 ライブラリを登録するには、<xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> メソッドを呼び出します。 要求を開始するツールに応じて、Visual Studio オブジェクトマネージャーは適切なライブラリを検索し、データを要求します。 データは、ライブラリと [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] オブジェクトマネージャーの間で、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2> インターフェイスによって記述されたシンボルの一覧に移動します。

 @No__t_0 オブジェクトマネージャーは、ライブラリに格納されている最新のデータを反映するために、シンボル参照ツールを定期的に更新する役割を担います。

 次の図には、ライブラリと Visual Studio オブジェクトマネージャー間の要求/データ交換プロセスの主要要素のサンプルが含まれています。 図のインターフェイスは、マネージコードアプリケーションの一部です。

 ![ライブラリとオブジェクトマネージャーの間のデータフロー](../../extensibility/internals/media/callbrowserdiagram.gif "CallBrowserDiagram")

 Visual Studio オブジェクトマネージャーにシンボルの一覧を提供するには、まず、<xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> メソッドを呼び出して、Visual Studio オブジェクトマネージャーにライブラリを登録する必要があります。 ライブラリが登録されると、Visual Studio のオブジェクトマネージャーによって、ライブラリの機能に関する特定の情報が要求されます。 たとえば、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetLibFlags2%2A> および <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetSupportedCategoryFields2%2A> メソッドを呼び出すことによって、ライブラリフラグとサポートされているカテゴリを要求します。 ある時点で、いずれかのツールがこのライブラリからデータを要求すると、オブジェクトマネージャーは <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetList2%2A> メソッドを呼び出すことによって、最上位レベルのシンボルリストを要求します。 応答として、ライブラリはシンボルの一覧を製造し、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2> インターフェイスを使用して、それを Visual Studio オブジェクトマネージャーに公開します。 @No__t_0 オブジェクトマネージャーは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetItemCount%2A> メソッドを呼び出すことによって、リストに含まれる項目の数を決定します。 次の要求はすべて、リスト内の特定の項目に関連付けられ、各要求に項目のインデックス番号を指定します。 Visual Studio オブジェクトマネージャーは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetCategoryField2%2A> メソッドを呼び出すことにより、項目の型、アクセシビリティ、およびその他のプロパティに関する情報を収集します。

 @No__t_0 メソッドを呼び出して項目の名前を決定し、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetDisplayData%2A> メソッドを呼び出すことによってアイコン情報を要求します。 項目名の左側にアイコンが表示され、項目の種類、アクセシビリティ、およびその他のプロパティが示されます。

 @No__t_0 オブジェクトマネージャーは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetExpandable3%2A> メソッドを呼び出して、特定のリスト項目が展開可能で、子項目があるかどうかを判断します。 UI が要素を展開する要求を送信する場合、オブジェクトマネージャーは <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetList2%2A> メソッドを呼び出すことによって、シンボルの子リストを要求します。 プロセスは、ツリーのさまざまな部分を必要に応じて構築し続けます。

> [!NOTE]
> ネイティブコードシンボルプロバイダーを実装するには、<xref:Microsoft.VisualStudio.Shell.Interop.IVsLibrary2> および <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectList2> インターフェイスを使用します。

## <a name="see-also"></a>関連項目
- [方法: オブジェクト マネージャーを使用したライブラリの登録](../../extensibility/internals/how-to-register-a-library-with-the-object-manager.md)
- [方法: ライブラリによって提供されるシンボルのリストをオブジェクト マネージャーに公開する](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)
- [方法: ライブラリでのシンボルの識別](../../extensibility/internals/how-to-identify-symbols-in-a-library.md)