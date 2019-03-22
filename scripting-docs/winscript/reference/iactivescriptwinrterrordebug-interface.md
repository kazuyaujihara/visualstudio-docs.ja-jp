---
title: IActiveScriptWinRTErrorDebug インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptWinRTErrorDebug Interface
ms.assetid: 58b45096-633f-479f-95c4-8eae7376d3a1
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 60fbe5efe55b5347eb54eb4d6c010b6ab5903905
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144239"
---
# <a name="iactivescriptwinrterrordebug-interface"></a>IActiveScriptWinRTErrorDebug インターフェイス
拡張の Windows ランタイム エラー情報を提供する JavaScript エンジンによって実装される、 [BREAKREASON 列挙型](../../winscript/reference/breakreason-enumeration.md)イベント。 取得する QueryInterface を行うことができます、 [IActiveScriptError](../../winscript/reference/iactivescripterror.md)オブジェクト。  
  
> [!IMPORTANT]
>  このインターフェイスは、PDM v11.0 以降によって実装されます。 activdbg100.h にあります。  
  
## <a name="methods"></a>メソッド  
 `IActiveScriptWinRTErrorDebug` インターフェイスは、以下のメソッドを公開します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptWinRTErrorDebug::GetCapabilitySid](../../winscript/reference/iactivescriptwinrterrordebug-getcapabilitysid.md)|使用可能な場合は、Windows ランタイム エラーでは、機能の SID を返します。|  
|[IActiveScriptWinRTErrorDebug::GetRestrictedErrorReference](../../winscript/reference/iactivescriptwinrterrordebug-getrestrictederrorreference.md)|返します、Windows ランタイムには、使用可能な場合のエラーの参照の文字列が制限されています。|  
|[IActiveScriptWinRTErrorDebug::GetRestrictedErrorString](../../winscript/reference/iactivescriptwinrterrordebug-getrestrictederrorstring.md)|返します、Windows ランタイムでは、使用可能な場合、エラーの文字列が制限されています。|