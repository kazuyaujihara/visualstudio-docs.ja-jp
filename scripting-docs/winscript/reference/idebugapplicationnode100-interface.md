---
title: IDebugApplicationNode100 インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNode100 Interface
ms.assetid: 43966d4e-5f89-4a04-a08d-782347d00c2d
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f380245422047142b3f06757f6c1057302dd5d26
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58146046"
---
# <a name="idebugapplicationnode100-interface"></a>IDebugApplicationNode100 インターフェイス
`IDebugApplicationNode100`インターフェイスの機能を拡張する、 [IDebugApplicationNode インターフェイス](../../winscript/reference/idebugapplicationnode-interface.md)します。 実装の QueryInterface を呼び出すことによってこのインターフェイスのインスタンスを取得できる[IDebugApplicationNode インターフェイス](../../winscript/reference/idebugapplicationnode-interface.md)します。  
  
> [!IMPORTANT]
>  このインターフェイスは、PDM v10.0 によって以降に実装されます。 activdbg100.h にあります。  
  
## <a name="methods"></a>メソッド  
 `IDebugApplicationNode100` インターフェイスは、以下のメソッドを公開します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugApplicationNode100::GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md)|指定したフィルターによって隠ぺいされているテキスト ドキュメントを取得します。|  
|[IDebugApplicationNode100::QueryIsChildNode](../../winscript/reference/idebugapplicationnode100-queryischildnode.md)|このノードの子ノードのいずれかに指定されたドキュメントが属しているかどうかを判断します。|  
|[IDebugApplicationNode100::SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)|特定のフィルターを設定[IDebugApplicationNodeEvents インターフェイス](../../winscript/reference/idebugapplicationnodeevents-interface.md)実装します。 PDM は、ノードが作成または削除されたときにイベントを送信できなくなるように、アプリケーションのコンパイラ生成の子ノードをフィルターするスクリプト デバッガーができます。 既定では、すべてのノードが送信されます。|