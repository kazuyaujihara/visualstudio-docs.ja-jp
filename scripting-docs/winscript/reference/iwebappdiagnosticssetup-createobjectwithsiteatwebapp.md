---
title: IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp |Microsoft Docs
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
ms.openlocfilehash: 26403a168268e817644637544d64d4205c398b75
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58157660"
---
# <a name="iwebappdiagnosticssetupcreateobjectwithsiteatwebapp"></a>IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp
このメソッドはクラスに渡す ID を持つ共同作成`rclsid`を使用して、`dwClsContext`します。 これは、方法に似ています[IRemoteDebugApplication::CreateInstanceAtApplication](../../winscript/reference/iremotedebugapplication-createinstanceatapplication.md)ことの場合を除いて、works`CreateObjectWithSiteAtWebApp`オブジェクトは、web アプリケーションの UI スレッドで非同期的に作成されます。 クラス ID で指定されたオブジェクトを実装する必要があります[IWebAppDiagnosticsObjectInitialization インターフェイス](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md)します。 オブジェクトが作成されたら、 [IWebAppDiagnosticsObjectInitialization::Initialize](../../winscript/reference/iwebappdiagnosticsobjectinitialization-initialize.md) PDM デバッグ アプリケーションへの参照を使用して呼び出したと`hPassToObject`パラメーターの`CreateObjectWithSiteAtWebApp`します。 このメソッドを使用するには、匿名パイプを使用してコピーしたにハンドルをアプリに渡す[DuplicateHandle](http://go.microsoft.com/fwlink/?LinkId=232450)します。  
  
> [!IMPORTANT]
>  [IWebAppDiagnosticsSetup インターフェイス](../../winscript/reference/iwebappdiagnosticssetup-interface.md)PDM v11.0 以降によって実装された以降には。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT CreateObjectWithSiteAtWebApp(        [in] REFCLSID rclsid,         [in] DWORD dwClsContext,         [in] REFIID riid,         [in] DWORD_PTR hPassToObject        );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `rclsid`  
 作成するクラスのクラス ID。  
  
 `dwClsContext`  
 コードを実行するコンテキスト。 ほとんどの場合は、CLSCTX_INPROC_SERVER を勧めします。  
  
 `riid`  
 使用しません。  
  
 `hPassToObject`  
 渡されるオブジェクトに、UI スレッドで作成した後、オブジェクトが実装されている場合、値[IWebAppDiagnosticsObjectInitialization インターフェイス](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md)します。