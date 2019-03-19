---
title: ISetNextStatement::SetNextStatement |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISetNextStatement.SetNextStatement
apilocation:
- scrobj.dll
ms.assetid: c5534f3b-39a5-4466-b8fc-69b717c6eee9
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3f4add20384684b24a630a0799c50a9aaae58034
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58148009"
---
# <a name="isetnextstatementsetnextstatement"></a>ISetNextStatement::SetNextStatement
このメソッドは、スクリプト インタープリターが実行できる次のコードのコンテキストを更新します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT SetNextStatement(  
   IDebugStackFrame*  pStackFrame,  
   IDebugCodeContext*  pCodeContext  
)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pStackFrame`  
 [in]スタック フレーム オブジェクトへのポインター。  
  
 `pCodeContext`  
 [in]コードのコンテキスト オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [ISetNextStatement インターフェイス](../../winscript/reference/isetnextstatement-interface.md)