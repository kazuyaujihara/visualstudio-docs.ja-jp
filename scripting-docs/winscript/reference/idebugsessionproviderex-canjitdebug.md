---
title: IDebugSessionProviderEx:CanJITDebug |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugSessionProviderEx:CanJITDebug
apilocation:
- scrobj.dll
ms.assetid: 68f91bed-ca69-46b5-b517-ca9ca80b8803
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 295be698e02264c81522b70d0377c2030da6190e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58154700"
---
# <a name="idebugsessionproviderexcanjitdebug"></a>IDebugSessionProviderEx:CanJITDebug
指定されたプロセスをジャスト イン タイムのデバッグがデバッグ対象にできるかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CanJITDebug(  
   DWORD  pid  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pid`  
 [in]デバッグするプロセスのプロセス識別子。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IDebugSessionProviderEx インターフェイス](../../winscript/reference/idebugsessionproviderex-interface.md)