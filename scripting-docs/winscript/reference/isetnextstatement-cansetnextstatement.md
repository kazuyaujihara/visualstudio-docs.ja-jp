---
title: 'ISetNextStatement:: CanSetNextStatement |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISetNextStatement.CanSetNextStatement
apilocation:
- scrobj.dll
ms.assetid: e2a54634-31ec-4d16-84e8-2b123845d876
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 56cf0b2e4afd7a86a087b37be4b23758a5b59720
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571844"
---
# <a name="isetnextstatementcansetnextstatement"></a>ISetNextStatement::CanSetNextStatement
このメソッドは、実行される次のコードステートメントを決定する実行ポイントが、指定された場所に設定できるかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CanSetNextStatement(  
   IDebugStackFrame*  pStackFrame,  
   IDebugCodeContext*  pCodeContext  
)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pStackFrame`  
 からスタックフレームオブジェクトへのポインター。  
  
 `pCodeContext`  
 からコードコンテキストオブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|次のステートメントは、指定されたコードコンテキストに更新できます。|  
|`S_FALSE`|次のステートメントは、指定されたコードコンテキストに更新できません。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [ISetNextStatement インターフェイス](../../winscript/reference/isetnextstatement-interface.md)