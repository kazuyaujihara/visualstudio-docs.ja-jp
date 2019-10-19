---
title: IDebugApplicationNodeEvents Interface |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNodeEvents interface
ms.assetid: 02e0bb17-84ce-458b-bae6-608a9899e535
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a2f72290e331a51f1b33746b22a6526c9bfbac7b
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574717"
---
# <a name="idebugapplicationnodeevents-interface"></a>IDebugApplicationNodeEvents インターフェイス
`IDebugApplicationNode` インターフェイスに対するイベント インターフェイスを提供します。  
  
 @No__t_1 インターフェイスは、`IUnknown` から継承されたメソッドに加えて、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugApplicationNodeEvents::onAddChild](../../winscript/reference/idebugapplicationnodeevents-onaddchild.md)|子ノードがデバッグアプリケーションのノードオブジェクトに追加されると、イベントを処理します。|  
|[IDebugApplicationNodeEvents::onRemoveChild](../../winscript/reference/idebugapplicationnodeevents-onremovechild.md)|デバッグアプリケーションノードオブジェクトから子ノードが削除されると、イベントを処理します。|  
|[IDebugApplicationNodeEvents::onDetach](../../winscript/reference/idebugapplicationnodeevents-ondetach.md)|デバッグアプリケーションノードオブジェクトが親ノードからデタッチされたことを示すイベントを処理します。|  
|[IDebugApplicationNodeEvents::onAttach](../../winscript/reference/idebugapplicationnodeevents-onattach.md)|デバッグアプリケーションノードオブジェクトが親ノードにアタッチされたことを示すイベントを処理します。|  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplicationNode インターフェイス](../../winscript/reference/idebugapplicationnode-interface.md)