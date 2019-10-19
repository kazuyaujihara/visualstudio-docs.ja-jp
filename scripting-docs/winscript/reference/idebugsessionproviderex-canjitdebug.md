---
title: 'IDebugSessionProviderEx: CanJITDebug |Microsoft Docs'
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
ms.openlocfilehash: d1ad9192d8faac9931cd3d14e688ee2f54e46687
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574921"
---
# <a name="idebugsessionproviderexcanjitdebug"></a>IDebugSessionProviderEx:CanJITDebug
指定されたプロセスを Just-in-time デバッグでデバッグできるかどうかを決定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CanJITDebug(  
   DWORD  pid  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pid`  
 からデバッグするプロセスのプロセス識別子。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IDebugSessionProviderEx インターフェイス](../../winscript/reference/idebugsessionproviderex-interface.md)