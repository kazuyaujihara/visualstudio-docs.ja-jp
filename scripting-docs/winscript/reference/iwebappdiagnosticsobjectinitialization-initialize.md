---
title: IWebAppDiagnosticsObjectInitialization::Initialize |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IWebAppDiagnosticsObjectInitialization::Initialize
ms.assetid: 7ccfac28-9f65-4e1c-a0fb-a8a6c7f75b63
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e7d3a3f966563e9d32294547ad604246ccd046e3
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446209"
---
# <a name="iwebappdiagnosticsobjectinitializationinitialize"></a>IWebAppDiagnosticsObjectInitialization::Initialize
作成されるオブジェクトを初期化します[IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md)します。  
  
> [!IMPORTANT]
> [IWebAppDiagnosticsObjectInitialization インターフェイス](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md)が見つかった activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT Initialize(        [in, annotation("__in")] HANDLE_PTR hPassedHandle,        [in, annotation("__in")] IUnknown* pDebugApplication        );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hPassedHandle`  
 渡されたハンドル、 [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md)メソッドで、`hPassToObject`パラメーター。  
  
 `pDebugApplication`  
 オブジェクトが作成された PDM アプリケーション。