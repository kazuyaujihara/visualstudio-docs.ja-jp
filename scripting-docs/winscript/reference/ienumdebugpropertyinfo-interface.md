---
title: IEnumDebugPropertyInfo Interface |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IEnumDebugPropertyInfo interface
ms.assetid: c5eea4da-8414-408a-a8f6-6a9ca8745868
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0ce4f5a114629a473df99b583c77ae7747bcd339
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574180"
---
# <a name="ienumdebugpropertyinfo-interface"></a>IEnumDebugPropertyInfo インターフェイス
@No__t_0 構造体を列挙します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 次の表は、`IEnumDebugPropertyInfo` のメソッドを示しています。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IEnumDebugPropertyInfo::Next](../../winscript/reference/ienumdebugpropertyinfo-next.md)|列挙シーケンス内の指定された数の `DebugPropertyInfo` 構造体を取得します。|  
|[IEnumDebugPropertyInfo::Skip](../../winscript/reference/ienumdebugpropertyinfo-skip.md)|列挙シーケンス内の指定された数の `DebugPropertyInfo` 構造体をスキップします。|  
|[IEnumDebugPropertyInfo::Reset](../../winscript/reference/ienumdebugpropertyinfo-reset.md)|列挙のシーケンスを最初にリセットします。|  
|[IEnumDebugPropertyInfo::Clone](../../winscript/reference/ienumdebugpropertyinfo-clone.md)|現在の列挙子と同じ列挙状態を含む列挙子を作成します。|  
|[IEnumDebugPropertyInfo::GetCount](../../winscript/reference/ienumdebugpropertyinfo-getcount.md)|列挙子内の `DebugPropertyInfo` 構造体の数を取得します。|  
  
## <a name="requirements"></a>［要件］  
 ヘッダー: dbgprop. h  
  
## <a name="see-also"></a>関連項目  
 [DebugPropertyInfo 構造体](../../winscript/reference/debugpropertyinfo-structure.md)