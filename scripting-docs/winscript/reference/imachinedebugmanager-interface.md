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
ms.openlocfilehash: 9d491b03ba04d346e3a14a08d5e2b6b9d34c7d97
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573929"
---
# <a name="imachinedebugmanager-interface"></a>IMachineDebugManager インターフェイス
マシンデバッグマネージャーへのプライマリインターフェイス。 このインターフェイスは `IMachineDebugManagerCookie` インターフェイスに似ています。  
  
 @No__t_1 インターフェイスは、`IUnknown` から継承されたメソッドに加えて、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IMachineDebugManager::AddApplication](../../winscript/reference/imachinedebugmanager-addapplication.md)|実行中のアプリケーションの一覧にアプリケーションを追加します。|  
|[IMachineDebugManager::RemoveApplication](../../winscript/reference/imachinedebugmanager-removeapplication.md)|実行中のアプリケーションの一覧からアプリケーションを削除します。|  
|[IMachineDebugManager::EnumApplications](../../winscript/reference/imachinedebugmanager-enumapplications.md)|実行中のアプリケーションの現在の一覧の列挙子を返します。|  
  
## <a name="see-also"></a>関連項目  
 [IMachineDebugManagerCookie インターフェイス](../../winscript/reference/imachinedebugmanagercookie-interface.md)