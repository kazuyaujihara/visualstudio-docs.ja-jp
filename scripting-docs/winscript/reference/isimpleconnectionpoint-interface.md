---
title: ISimpleConnectionPoint Interface |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- ISimpleConnectionPoint interface
ms.assetid: f632a82f-942d-4291-963e-e9fa2b162493
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 549d7f38b01937f992b240cb6f1d651bc848236c
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571795"
---
# <a name="isimpleconnectionpoint-interface"></a>ISimpleConnectionPoint インターフェイス
特定のコネクションポイントで発生したイベントを記述および列挙するための簡単な方法を提供します。 また、このインターフェイスを使用すると、`IDispatch` オブジェクトをそれらのイベントに簡単にフックできます。 このインターフェイスは、プロセスデバッグマネージャー (PDM) によって実装され、スクリプトエンジンによって使用されます。  
  
 このインターフェイスは `IDebugHelper::CreateSimpleConnectionPoint` から使用できます。  
  
 @No__t_1 インターフェイスは、`IUnknown` から継承されたメソッドに加えて、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[ISimpleConnectionPoint::Advise](../../winscript/reference/isimpleconnectionpoint-advise.md)|単純な接続ポイントオブジェクトとクライアントのシンクとの間の接続を確立します。|  
|[ISimpleConnectionPoint::DescribeEvents](../../winscript/reference/isimpleconnectionpoint-describeevents.md)|指定されたイベントの範囲内の各イベントの DISPID と名前を返します。|  
|[ISimpleConnectionPoint::GetEventCount](../../winscript/reference/isimpleconnectionpoint-geteventcount.md)|このインターフェイスで公開されているイベントの数を返します。|  
|[ISimpleConnectionPoint::Unadvise](../../winscript/reference/isimpleconnectionpoint-unadvise.md)|以前に `ISimpleConnectionPoint::Advise` によって確立されたアドバイザリコネクションを終了します。|  
  
## <a name="see-also"></a>関連項目  
 [IDebugProperty インターフェイス](../../winscript/reference/idebugproperty-interface.md)