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
ms.openlocfilehash: 38ab73ddb1bd924035cb6ba61d26e65f16f53eed
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577517"
---
# <a name="iscriptnode-interface"></a>IScriptNode インターフェイス
@No__t_0 インターフェイスを実装するオブジェクトは、Web ページを表します。  
  
 @No__t_1 インターフェイスは、`IUnknown` から継承されたメソッドに加えて、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IScriptNode::Alive](../../winscript/reference/iscriptnode-alive.md)|オブジェクトがまだアクティブであるかどうかを示します。|  
|[IScriptNode:: CreateChildEntry](../../winscript/reference/iscriptnode-createchildentry.md)|@No__t_0 の子インスタンスを追加します。|  
|[IScriptNode::CreateChildHandler](../../winscript/reference/iscriptnode-createchildhandler.md)|@No__t_0 の子インスタンスとしてスクリプトレットを追加します。|  
|[IScriptNode::Delete](../../winscript/reference/iscriptnode-delete.md)|オブジェクトツリーを削除します。|  
|[IScriptNode::GetChild](../../winscript/reference/iscriptnode-getchild.md)|ノード内の指定したインデックス位置にある子を返します。|  
|[IScriptNode::GetCookie](../../winscript/reference/iscriptnode-getcookie.md)|スクリプトレットをホストオブジェクトに関連付けるために使用される、アプリケーション定義の値を返します。|  
|[IScriptNode::GetIndexInParent](../../winscript/reference/iscriptnode-getindexinparent.md)|親の子リスト内のオブジェクトのインデックスを返します。|  
|[IScriptNode::GetLanguage](../../winscript/reference/iscriptnode-getlanguage.md)|現在のスクリプトノードによって使用されているスクリプト言語を返します。|  
|[IScriptNode::GetNumberOfChildren](../../winscript/reference/iscriptnode-getnumberofchildren.md)|@No__t_0 オブジェクトの子ノードの数を返します。|  
|[IScriptNode::GetParent](../../winscript/reference/iscriptnode-getparent.md)|オブジェクトの親である `IScriptNode` オブジェクトを返します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト作成インターフェイス](../../winscript/reference/active-script-authoring-interfaces.md)