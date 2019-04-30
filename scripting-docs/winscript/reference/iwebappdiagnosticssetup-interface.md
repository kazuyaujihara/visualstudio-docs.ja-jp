---
title: IWebAppDiagnosticsSetup インターフェイス |Microsoft Docs
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
ms.openlocfilehash: 71d4501fff04b62abe392c6684a4a0551dea9ee8
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63443664"
---
# <a name="iwebappdiagnosticssetup-interface"></a>IWebAppDiagnosticsSetup インターフェイス
このインターフェイスは、PDM デバッグ アプリケーションは、デバッグ中のプロセスで COM オブジェクトを作成し、web の診断を有効にして実装されます。 PDM は、アプリケーション オブジェクトの実装をデバッグする場合[IObjectWithSite](http://go.microsoft.com/fwlink/?LinkId=232438)、Internet Explorer を呼び出す[SetSite](http://go.microsoft.com/fwlink/?LinkId=232439)が作成された後、およびパスへの参照の[IWebBrowser2](http://go.microsoft.com/fwlink/?LinkId=232449). WWA アプリケーションが呼び出す[SetSite](http://go.microsoft.com/fwlink/?LinkId=232439)とインターフェイス IWebApplicationHost の代わりに、WWA で渡します。 場合[SetSite](http://go.microsoft.com/fwlink/?LinkId=232439)は NULL 以外の値で呼び出されました[IWebAppDiagnosticsSetup::DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md) true を返します。 場合は、false を返し、呼び出し[IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md)失敗します。  
  
> [!IMPORTANT]
> `IWebAppDiagnosticsSetup` 以降 PDM v11.0 以降によって実装されます。 activdbg100.h にあります。  
  
## <a name="methods"></a>メソッド  
 このインターフェイスは、次のメソッドを公開します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md)|指定したフィルターによって隠ぺいされているテキスト ドキュメントを取得します。|  
|[IWebAppDiagnosticsSetup::DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md)|このノードの子ノードのいずれかに指定されたドキュメントが属しているかどうかを判断します。|