---
title: カスタムエディターの構文の色分け |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - syntax coloring
ms.assetid: 74900b9a-baef-432a-8231-4568fb5e19ad
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f4302f463d93776d17be0251e6194375c15adc19
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72718768"
---
# <a name="syntax-coloring-in-custom-editors"></a>カスタム エディターでの構文の色分け表示
コアエディターなどの Visual Studio 環境 SDK エディターでは、言語サービスを使用して特定の構文項目を識別し、特定のドキュメントビューに対して指定した色で表示します。

## <a name="colorization-requirements"></a>色付けの要件
 言語サービスの色を実装するすべてのエディターでは、次のことを行う必要があります。

1. @No__t_0 を実装するオブジェクトを使用して、着色するテキストを管理し、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> を実装するオブジェクトを使用して、テキストのドキュメントビューを提供します。

2. 言語サービスの識別 GUID を使用して VSPackage のサービスプロバイダーを照会することによって、特定の言語サービスへのインターフェイスを取得します。

3. @No__t_1 を実装するオブジェクトの <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> メソッドを呼び出します。 このメソッドは、VSPackage が色分けされるテキストを管理するために使用する <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 実装に言語サービスを関連付けます。

## <a name="core-editor-usage-of-a-language-services-colorizer"></a>言語サービスの Colorizer いるコアエディターの使用
 カラーを使用する言語サービスがコアエディターのインスタンスによって取得されると、言語サービスの colorartifactによるテキストの解析とレンダリングが自動的に行われます。

 IDE は透過的に行われます。

- @No__t_0 の実装で追加または変更されたときに、必要に応じてカラーを呼び出して、テキストを解析および分析します。

- @No__t_0 実装によって提供されるドキュメントビューによって提供される表示が更新され、colorizer 返された情報を使用して再描画されることを保証します。

## <a name="non-core-editor-usage-of-a-language-services-colorizer"></a>言語サービスの色覚計の非コアエディターの使用
 非コアエディターインスタンスでは、言語サービスの構文色付けサービスも使用できますが、サービスの colorizer 明示的に取得して適用し、ドキュメントビュー自体を再描画する必要があります。

 これを行うには、非コアエディターで次の操作を行う必要があります。

1. 言語サービスの colorizer オブジェクト (<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> と <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer2> を実装する) を取得します。 VSPackage は、言語サービスのインターフェイスで <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> メソッドを呼び出すことによってこれを行います。

2. @No__t_0 メソッドを呼び出して、テキストの特定の範囲が色分けされるように要求します。

     @No__t_0 メソッドは、色分けされたテキスト範囲内の各文字に対して1つずつ、値の配列を返します。 また、装飾 item の特定の型 (コメント、キーワード、データ型など) として、テキスト範囲を識別します。

3. @No__t_0 によって返された色付け情報を使用して、そのテキストを再描画して表示します。

> [!NOTE]
> 言語サービスの colorizer を使用するだけでなく、汎用的な Visual Studio 環境 SDK テキストの色分け機構を使用することもできます。 このメカニズムの詳細については、「[フォントおよび色の使用](../extensibility/using-fonts-and-colors.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [従来の言語サービスでの構文の色分け表示](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)
- [構文の色分け表示の実装](../extensibility/internals/implementing-syntax-coloring.md)
- [方法: ビルトインの配色可能な項目の使用](../extensibility/internals/how-to-use-built-in-colorable-items.md)
- [カスタムの配色可能な項目](../extensibility/internals/custom-colorable-items.md)