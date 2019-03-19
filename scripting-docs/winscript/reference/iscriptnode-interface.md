---
title: IScriptNode インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IScriptNode interface
ms.assetid: cfa76c4a-6543-48e8-a946-d212cd0bf934
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 13bf20f9e1e642b948ddaa72ae9dca7bb457fba2
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58155840"
---
# <a name="iscriptnode-interface"></a>IScriptNode インターフェイス
実装するオブジェクト、`IScriptNode`インターフェイスが Web ページを表します。  
  
 継承されたメソッドだけでなく`IUnknown`、`IScriptNode`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IScriptNode::Alive](../../winscript/reference/iscriptnode-alive.md)|オブジェクトがまだアクティブかどうかを示します。|  
|[IScriptNode::CreateChildEntry](../../winscript/reference/iscriptnode-createchildentry.md)|子インスタンスを追加します。`IScriptEntry`します。|  
|[IScriptNode::CreateChildHandler](../../winscript/reference/iscriptnode-createchildhandler.md)|子インスタンスとしてスクリプトレットを追加、`IScriptNode`します。|  
|[IScriptNode::Delete](../../winscript/reference/iscriptnode-delete.md)|オブジェクト ツリーを削除します。|  
|[IScriptNode::GetChild](../../winscript/reference/iscriptnode-getchild.md)|ノードで指定したインデックス位置にある子を返します。|  
|[IScriptNode::GetCookie](../../winscript/reference/iscriptnode-getcookie.md)|スクリプトレットを関連付けるホスト オブジェクトに使用するアプリケーション定義の値を返します。|  
|[IScriptNode::GetIndexInParent](../../winscript/reference/iscriptnode-getindexinparent.md)|親の子の一覧で、オブジェクトのインデックスを返します。|  
|[IScriptNode::GetLanguage](../../winscript/reference/iscriptnode-getlanguage.md)|スクリプトの現在のノードで使用されるスクリプト言語を返します。|  
|[IScriptNode::GetNumberOfChildren](../../winscript/reference/iscriptnode-getnumberofchildren.md)|子ノードの数を返します、`IScriptNode`オブジェクト。|  
|[IScriptNode::GetParent](../../winscript/reference/iscriptnode-getparent.md)|返します、`IScriptNode`オブジェクトの親であるオブジェクト。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト作成インターフェイス](../../winscript/reference/active-script-authoring-interfaces.md)