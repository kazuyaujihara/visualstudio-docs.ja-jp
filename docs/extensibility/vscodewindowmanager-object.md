---
title: VSCodeWindowManager オブジェクト |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VSCodeWindowManager
helpviewer_keywords:
- VsCodeWindowManager object
- views [Visual Studio SDK], VSCodeWindowManager object
ms.assetid: e313add5-afdb-4d8d-abd1-764e1fc10c44
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c67fb719c6ec87e7707a406e2e7f67cd71569b39
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73189038"
---
# <a name="vscodewindowmanager-object"></a>VSCodeWindowManager オブジェクト

言語サービスはコードウィンドウマネージャーを実装し、修飾 (ドロップダウンバーなど) の管理を担当します。 詳細については、「[従来の API を使用してコードウィンドウをカスタマイズする](/visualstudio/extensibility/customizing-code-windows-by-using-the-legacy-api?view=vs-2015)」を参照してください。

次の表は、`VSCodeWindowManager` オブジェクト内のインターフェイスを示しています。

|Interface|説明|
|---------------|-----------------|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>|コードウィンドウに対する修飾 (ドロップダウンバーなど) の追加または削除を許可します。|