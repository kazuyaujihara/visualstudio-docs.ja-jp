---
title: IMachineDebugManager インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IMachineDebugManager interface
ms.assetid: 0b7133bb-5a52-4036-b4db-d69260790db7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6db8989fc6c932723a9b95017854635396b0deda
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58157962"
---
# <a name="imachinedebugmanager-interface"></a>IMachineDebugManager インターフェイス
マシン デバッグ マネージャーの主インターフェイスです。 このインターフェイスと似ています、`IMachineDebugManagerCookie`インターフェイス。  
  
 継承されたメソッドだけでなく`IUnknown`、`IMachineDebugManager`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IMachineDebugManager::AddApplication](../../winscript/reference/imachinedebugmanager-addapplication.md)|実行中にアプリケーションを追加します。 アプリケーションの一覧。|  
|[IMachineDebugManager::RemoveApplication](../../winscript/reference/imachinedebugmanager-removeapplication.md)|実行中のアプリケーションを削除します。 アプリケーションの一覧。|  
|[IMachineDebugManager::EnumApplications](../../winscript/reference/imachinedebugmanager-enumapplications.md)|現在の実行中のアプリケーション一覧の列挙子を返します。|  
  
## <a name="see-also"></a>関連項目  
 [IMachineDebugManagerCookie インターフェイス](../../winscript/reference/imachinedebugmanagercookie-interface.md)