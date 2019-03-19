---
title: IMachineDebugManagerCookie インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IMachineDebugManagerCookie interface
ms.assetid: 04770935-3ccf-41e9-b0c1-c78376ab1e3c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fdc02498360f2e3900012166474c5d1e35abd6ee
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58151051"
---
# <a name="imachinedebugmanagercookie-interface"></a>IMachineDebugManagerCookie インターフェイス
ような`IMachineDebugManager`、インターフェイス、`IMachineDebugManagerCookie`インターフェイスはデバッグ cookie をサポートしています。  
  
 このインターフェイス (と共に、`IDebugCookie`インターフェイス)、デバッガーの追跡のスクリプトを必要とせずにスクリプト デバッガー プロセスで実行するスクリプトを許可します。  
  
 スクリプト デバッガーを呼び出して、`IDebugCookie::SetDebugCookie`メソッド プロセス デバッグ マネージャー (PDM)。 次に、PDM 送信を追加または削除から、マシン デバッグ マネージャー (MDM)、またはスクリプト アプリケーションのすべての要求と共にこの cookie のメソッドを使用して、`IMachineDebugManagerCookie`インターフェイス。 MDM の変更は、そのクッキーのあるものを除くすべてのデバッガーを通知します。  
  
 継承されたメソッドだけでなく`IUnknown`、`IMachineDebugManagerCookie`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IMachineDebugManagerCookie::AddApplication](../../winscript/reference/imachinedebugmanagercookie-addapplication.md)|実行中にアプリケーションを追加します。 アプリケーションの一覧。|  
|[IMachineDebugManagerCookie::EnumApplications](../../winscript/reference/imachinedebugmanagercookie-enumapplications.md)|現在の実行中のアプリケーション一覧の列挙子を返します。|  
|[IMachineDebugManagerCookie::RemoveApplication](../../winscript/reference/imachinedebugmanagercookie-removeapplication.md)|実行中のアプリケーションを削除します。 アプリケーションの一覧。|  
  
## <a name="see-also"></a>関連項目  
 [IMachineDebugManager インターフェイス](../../winscript/reference/imachinedebugmanager-interface.md)   
 [IDebugCookie インターフェイス](../../winscript/reference/idebugcookie-interface.md)