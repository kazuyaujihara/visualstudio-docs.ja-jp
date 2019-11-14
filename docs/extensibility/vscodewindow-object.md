---
title: VSCodeWindow オブジェクト |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VSCodeWindow
helpviewer_keywords:
- views [Visual Studio SDK], VSCodeWindow object
- VsCodeWindow object
ms.assetid: cf5fe926-e784-4098-bc01-cac49c7c55c6
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 36b7e0e6806f88efe373dffa3f21ba79baefb281
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73189055"
---
# <a name="vscodewindow-object"></a>VSCodeWindow オブジェクト
コードウィンドウは、1つまたは複数のテキストビュー (通常は <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> オブジェクト) を含むことができる特殊なドキュメントウィンドウです。

 アーキテクチャ上、コードウィンドウはウィンドウフレーム内のドキュメントウィンドウです。 機能的には、コードウィンドウは単なるドキュメントウィンドウであり、追加機能があります。 マルチドキュメントインターフェイス (MDI) モードでは、コードウィンドウは MDI 子フレームです。 詳細については、「[従来の API を使用してコードウィンドウをカスタマイズする](/visualstudio/extensibility/customizing-code-windows-by-using-the-legacy-api?view=vs-2015)」を参照してください。

 次の表は、<xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> オブジェクト内のインターフェイスを示しています。

|メソッド|説明|
|------------|-----------------|
|<xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>|グローバル一意識別子 (GUID) によって識別されるサービスを検索するための汎用アクセス機構を提供します。|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|1つ以上のコードビューを含むマルチドキュメントインターフェイス (MDI) 子を表します。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|ウィンドウフレームを塗りつぶします。|

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>
- [図形の編集](https://www.microsoft.com/download/details.aspx?id=55984)