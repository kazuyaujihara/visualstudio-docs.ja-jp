---
title: 'IEnumDebugCodeContexts:: Skip |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugCodeContexts.Skip
apilocation:
- jscript.dll
helpviewer_keywords:
- IEnumDebugCodeContexts::Skip
ms.assetid: ba917f57-f7a9-419f-96d6-8f4378b12c57
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a16343b24a640341009758345b17f86e94b7b2ed
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577203"
---
# <a name="ienumdebugcodecontextsskip"></a>IEnumDebugCodeContexts::Skip
列挙シーケンス内の指定された数のセグメントをスキップします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Skip(  
   ULONG  celt  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `celt`  
 からスキップする列挙シーケンス内のセグメントの数。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、列挙シーケンス内の指定された数のセグメントをスキップします。  
  
## <a name="see-also"></a>関連項目  
 [IEnumDebugCodeContexts インターフェイス](../../winscript/reference/ienumdebugcodecontexts-interface.md)