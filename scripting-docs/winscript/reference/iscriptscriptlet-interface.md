---
title: IScriptScriptlet インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IScriptScriptlet interface
ms.assetid: b9981908-a337-4228-864c-c741f111ab2d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c11aada6b8c39c7dd5f0b2a6b30cdd837aa0edda
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58151259"
---
# <a name="iscriptscriptlet-interface"></a>IScriptScriptlet インターフェイス
実装するオブジェクト、`IScriptScriptlet`インターフェイスは、イベント ハンドラー スクリプトを表します。  
  
 継承されたメソッドだけでなく`IScriptEntry`、`IScriptScriptlet`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IScriptScriptlet::GetEventName](../../winscript/reference/iscriptscriptlet-geteventname.md)|スクリプトレットに関連付けられているイベントの名前を返します。|  
|[IScriptScriptlet::GetSimpleEventName](../../winscript/reference/iscriptscriptlet-getsimpleeventname.md)|スクリプトレットに関連付けられている単純なイベント名を返します。 任意の空白文字を含まない 1 単語の名前です。|  
|[IScriptScriptlet::GetSubItemName](../../winscript/reference/iscriptscriptlet-getsubitemname.md)|スクリプトレットのオブジェクトのホストの完全修飾名では、最後の識別子を返します。|  
|[IScriptScriptlet::SetEventName](../../winscript/reference/iscriptscriptlet-seteventname.md)|スクリプトレットに関連付けられているイベントの名前を設定します。|  
|[IScriptScriptlet::SetSimpleEventName](../../winscript/reference/iscriptscriptlet-setsimpleeventname.md)|スクリプトレットに関連付けられている単純なイベント名を設定します。 任意の空白文字を含まない 1 単語の名前です。|  
|[IScriptScriptlet::SetSubItemName](../../winscript/reference/iscriptscriptlet-setsubitemname.md)|スクリプトレットのオブジェクトのホストの完全修飾名では、最後の識別子を設定します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト作成インターフェイス](../../winscript/reference/active-script-authoring-interfaces.md)