---
title: IRemoteDebugApplication110::SetDebuggerOptions |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplication110::SetDebuggerOptions
ms.assetid: 58e9fd18-3e0d-47fa-8893-f316146bde84
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a61eabb307bda39fd871e8f5f4f7198256f0929e
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63383355"
---
# <a name="iremotedebugapplication110setdebuggeroptions"></a>IRemoteDebugApplication110::SetDebuggerOptions
デバッガーのオプションを更新するには、呼び出されます。 このメソッドは、後に呼び出す必要があります[IRemoteDebugApplication::ConnectDebugger](../../winscript/reference/iremotedebugapplication-connectdebugger.md)します。 [IRemoteDebugApplication::DisconnectDebugger](../../winscript/reference/iremotedebugapplication-disconnectdebugger.md)メソッドは、既定のオプションを自動的にリセットします。 0 (SDO_NONE) に既定のオプション。  
  
> [!IMPORTANT]
> [IRemoteDebugApplication インターフェイス](../../winscript/reference/iremotedebugapplication-interface.md)PDM v11.0 以降によって実装された以降には。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT SetDebuggerOptions(        [in] enum SCRIPT_DEBUGGER_OPTIONS mask,        [in] enum SCRIPT_DEBUGGER_OPTIONS value    );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `mask`  
 [SCRIPT_DEBUGGER_OPTIONS 列挙型](../../winscript/reference/script-debugger-options-enumeration.md)マスク。  
  
 `value`  
 [SCRIPT_DEBUGGER_OPTIONS 列挙型](../../winscript/reference/script-debugger-options-enumeration.md)値。  
  
## <a name="see-also"></a>関連項目  
 [IRemoteDebugApplication インターフェイス](../../winscript/reference/iremotedebugapplication-interface.md)   
 [IRemoteDebugApplication110 インターフェイス](../../winscript/reference/iremotedebugapplication110-interface.md)