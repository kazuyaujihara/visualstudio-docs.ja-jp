---
title: 従来の言語サービスでの構文の色分け |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- syntax coloring
- language services, syntax coloring
ms.assetid: f65ff67e-8c20-497a-bebf-5e2a5b5b012f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ffa3dcadfc7774766c0e76617ce133d2c30ba2aa
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73186312"
---
# <a name="syntax-coloring-in-a-legacy-language-service"></a>従来の言語サービスでの構文の色分け表示

Visual Studio は、色分けサービスを使用して言語の要素を識別し、エディターで指定された色でそれらを表示します。

## <a name="colorizer-model"></a>Colorizer モデル
 言語サービスは、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> インターフェイスを実装します。このインターフェイスは、エディターによって使用されます。 この実装は、次の図に示すように、言語サービスとは別のオブジェクトです。

 ![SVC Colorizer グラフィック](../../extensibility/internals/media/figlgsvccolorizer.gif)

> [!NOTE]
> 構文の色分け表示サービスは、色分け text の一般的な Visual Studio 機構とは別のものです。 色分けをサポートする一般的な [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] メカニズムの詳細については、「[フォントおよび色の使用](/visualstudio/extensibility/using-fonts-and-colors?view=vs-2015)」を参照してください。

 また、言語サービスでは、カスタムの装飾項目を提供することを通知することで、エディターで使用されるカスタム装飾項目を指定できます。 これを行うには、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> インターフェイスを実装するのと同じオブジェクトに <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> インターフェイスを実装します。 エディターが <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetItemCount%2A> メソッドを呼び出したときにカスタム装飾項目の数を返し、エディターが <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> メソッドを呼び出したときに個々のカスタム装飾項目を返します。

 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> メソッドは、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> インターフェイスを実装するオブジェクトを返します。 言語サービスで24ビットまたは高色の値がサポートされている場合は、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> インターフェイスと同じオブジェクトに <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> インターフェイスを実装する必要があります。

## <a name="how-a-vspackage-uses-a-language-service-colorizer"></a>VSPackage が言語サービスカラーを使用する方法

1. VSPackage は、適切な言語サービスを取得する必要があります。そのためには、言語サービス VSPackage で次の操作を行う必要があります。

    1. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> インターフェイスを実装するオブジェクトを使用して、着色するテキストを取得します。

         通常、テキストは、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> インターフェイスを実装するオブジェクトを使用して表示されます。

    2. 言語サービスの GUID を取得するには、VSPackage のサービスプロバイダーに対してクエリを実行します。 言語サービスは、レジストリのファイル拡張子によって識別されます。

    3. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> メソッドを呼び出すことによって、言語サービスを <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> に関連付けます。

2. VSPackage は、次のように colorizer オブジェクトを取得して使用できるようになりました。

    > [!NOTE]
    > コアエディターを使用する Vspackage では、言語サービスの colorizer オブジェクトを明示的に取得する必要はありません。 コアエディターのインスタンスは、適切な言語サービスを取得するとすぐに、ここに示されているすべての色付けタスクを実行します。

    1. 言語サービスの <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> オブジェクトの <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> メソッドを呼び出すことによって、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>、および <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer2> インターフェイスを実装する言語サービスの colorizer いるオブジェクトを取得します。

    2. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> メソッドを呼び出して、特定のテキスト範囲の色を取得します。

         <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> は、色分けされたテキスト範囲内の文字ごとに1つずつ、値の配列を返します。 値は、コアエディターによって管理される既定の装飾 item リスト、または言語サービス自体によって管理されるカスタム装飾項目リストの装飾 item リストにインデックスが付けられます。

    3. 選択したテキストを表示するには、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> メソッドによって返される色付け情報を使用します。

> [!NOTE]
> 言語サービスの colorizer を使用するだけでなく、汎用的な Visual Studio テキスト色分け機構を使用することもできます。 このメカニズムの詳細については、「[フォントおよび色の使用](/visualstudio/extensibility/using-fonts-and-colors?view=vs-2015)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容
- [構文の色分け表示の実装](../../extensibility/internals/implementing-syntax-coloring.md)

 エディターが言語サービスの構文の色分けにアクセスする方法と、構文の色分けをサポートするために言語サービスが実装する必要がある内容について説明します。

- [方法: ビルトインの配色可能な項目の使用](../../extensibility/internals/how-to-use-built-in-colorable-items.md)

 言語サービスの組み込みの装飾項目を使用する方法を示します。

- [カスタムの配色可能な項目](../../extensibility/internals/custom-colorable-items.md)

 カスタム装飾項目を実装する方法について説明します。