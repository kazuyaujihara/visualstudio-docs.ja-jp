---
title: IWebAppDiagnosticsSetup Interface |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IWebAppDiagnosticsSetup Interface
ms.assetid: ec7359f2-633e-4d59-b64b-9cab0134dfd0
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e9bb3905da6227b978bc27b96493500f8d6d2ff
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72984541"
---
# <a name="iwebappdiagnosticssetup-interface"></a>IWebAppDiagnosticsSetup インターフェイス
このインターフェイスは、デバッグ対象のプロセス内に COM オブジェクトを作成し、web 診断を有効にするために、PDM デバッグアプリケーションによって実装されます。 PDM デバッグアプリケーションオブジェクトが[IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite)を実装している場合、Internet Explorer は、作成後に[SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)を呼び出し、 [IWebBrowser2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752127(v=vs.85))への参照を渡します。 WWA アプリケーションは[SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)を呼び出し、代わりに wwa インターフェイス IWebApplicationHost を渡します。 [SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)が NULL 以外の値で呼び出された場合、 [IWebAppDiagnosticsSetup::D iagnosticssupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md)は true を返します。 そうでない場合は、false を返し、 [IWebAppDiagnosticsSetup:: CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md) fail を呼び出します。  
  
> [!IMPORTANT]
> `IWebAppDiagnosticsSetup` は、PDM version 11.0 以降で実装されています。 activdbg100.h にあります。  
  
## <a name="methods"></a>メソッド  
 このインターフェイスは、次のメソッドを公開します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md)|指定したフィルターによって非表示にされているテキストドキュメントを取得します。|  
|[IWebAppDiagnosticsSetup::DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md)|指定されたドキュメントが、このノードの子ノードのいずれかに属しているかどうかを判断します。|