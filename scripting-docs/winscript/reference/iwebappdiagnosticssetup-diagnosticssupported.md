---
title: IWebAppDiagnosticsSetup::D iagnosticsSupported |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IWebAppDiagnosticsSetup::DiagnosticsSupported
ms.assetid: 5bbcd0d0-1460-4cf7-bbb1-f4f4a04f739a
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd27e7c8759054fa2d7d67858d8d006fa9c9a152
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72984584"
---
# <a name="iwebappdiagnosticssetupdiagnosticssupported"></a>IWebAppDiagnosticsSetup::DiagnosticsSupported
このアプリケーションで診断がサポートされているかどうかを判断します。 このインターフェイスを実装するオブジェクトで、NULL 以外の値を使用して[SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)が呼び出された場合、 [DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md)は `true`を返します。 そうでない場合は `false` を返し、 [IWebAppDiagnosticsSetup:: CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md) fail を呼び出します。  
  
> [!IMPORTANT]
> [IWebAppDiagnosticsSetup インターフェイス](../../winscript/reference/iwebappdiagnosticssetup-interface.md)は、PDM version 11.0 以降で実装されています。 Activdbg100.h で見つかりました。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT DiagnosticsSupported(        [out, retval] VARIANT_BOOL* pRetVal        );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 このインターフェイスを実装するオブジェクトで、NULL 以外の値を使用して[SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)が呼び出された場合、 [DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md)は `true`を返します。 そうでない場合は `false`を返し、 [IWebAppDiagnosticsSetup:: CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md) fail を呼び出します。