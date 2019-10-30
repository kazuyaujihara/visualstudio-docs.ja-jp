---
title: 'IWebAppDiagnosticsSetup:: CreateObjectWithSiteAtWebApp |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp
ms.assetid: 30975973-acb1-48f4-8266-5e097a57db22
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 253b995c200566868ac9ccc06b259e0a152e1676
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72984606"
---
# <a name="iwebappdiagnosticssetupcreateobjectwithsiteatwebapp"></a>IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp
このメソッドは、`dwClsContext`を使用して `rclsid` に渡す ID を持つクラスを併置します。 これは[Iremotedebugapplication:: CreateInstanceAtApplication](../../winscript/reference/iremotedebugapplication-createinstanceatapplication.md)の動作と似ていますが、`CreateObjectWithSiteAtWebApp` の場合、web アプリケーションの UI スレッドでオブジェクトが非同期的に作成される点が異なります。 クラス ID で指定されたオブジェクトは、 [IWebAppDiagnosticsObjectInitialization インターフェイス](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md)を実装する必要があります。 オブジェクトが作成された後、 [IWebAppDiagnosticsObjectInitialization:: Initialize](../../winscript/reference/iwebappdiagnosticsobjectinitialization-initialize.md)は、PDM デバッグアプリケーションへの参照と `CreateObjectWithSiteAtWebApp`の `hPassToObject` パラメーターを使用して呼び出されます。 このメソッドを使用すると、 [DuplicateHandle](/windows/win32/api/handleapi/nf-handleapi-duplicatehandle)を使用してコピーした匿名パイプへのハンドルをアプリに渡すことができます。  
  
> [!IMPORTANT]
> [IWebAppDiagnosticsSetup インターフェイス](../../winscript/reference/iwebappdiagnosticssetup-interface.md)は、PDM version 11.0 以降で実装されています。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT CreateObjectWithSiteAtWebApp(        [in] REFCLSID rclsid,         [in] DWORD dwClsContext,         [in] REFIID riid,         [in] DWORD_PTR hPassToObject        );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `rclsid`  
 作成するクラスのクラス ID。  
  
 `dwClsContext`  
 コードを実行するコンテキスト。 ほとんどの場合、CLSCTX_INPROC_SERVER になります。  
  
 `riid`  
 使用しません。  
  
 `hPassToObject`  
 オブジェクトが[IWebAppDiagnosticsObjectInitialization インターフェイス](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md)を実装している場合、UI スレッドで作成されたオブジェクトに渡される値。