---
title: IWebAppDiagnosticsObjectInitialization インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IWebAppDiagnosticsObjectInitialization Interface
ms.assetid: 32847838-01d9-4205-a811-3043d8c7a917
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a992f8512d4927eeb58d6437ccb830abda688b28
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63443687"
---
# <a name="iwebappdiagnosticsobjectinitialization-interface"></a>IWebAppDiagnosticsObjectInitialization インターフェイス
このインターフェイスを実装するクラスに実装できます[IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md)します。 [IWebAppDiagnosticsSetup インターフェイス](../../winscript/reference/iwebappdiagnosticssetup-interface.md)を実装するオブジェクトによって実装されます[IDebugApplication インターフェイス](../../winscript/reference/idebugapplication-interface.md)します。 ほとんどの場合は、このオブジェクトは、PDM は。  
  
 オブジェクトが作成されたら、 [IWebAppDiagnosticsObjectInitialization::Initialize](../../winscript/reference/iwebappdiagnosticsobjectinitialization-initialize.md) PDM デバッグ アプリケーションへの参照を使用して呼び出したと`hPassToObject`パラメーターの`CreateObjectWithSiteAtWebApp`します。  
  
> [!IMPORTANT]
> `IWebAppDiagnosticsObjectInitialization` activdbg100.h にあります。  
  
## <a name="methods"></a>メソッド  
 このインターフェイスは、次のメソッドを公開します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IWebAppDiagnosticsObjectInitialization::Initialize](../../winscript/reference/iwebappdiagnosticsobjectinitialization-initialize.md)|オブジェクトを初期化します。|