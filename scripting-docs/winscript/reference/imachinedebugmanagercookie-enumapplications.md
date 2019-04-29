---
title: IMachineDebugManagerCookie::EnumApplications |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IMachineDebugManagerCookie.EnumApplications
apilocation:
- scrobj.dll
helpviewer_keywords:
- IMachineDebugManagerCookie::EnumApplications
ms.assetid: 03f863cf-fa7f-4ec4-b1a1-1ae0ad296c39
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 76d8e53d586a812f4a8416a1515d7011dd5a1720
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977618"
---
# <a name="imachinedebugmanagercookieenumapplications"></a>IMachineDebugManagerCookie::EnumApplications
現在の実行中のアプリケーション一覧の列挙子を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT EnumApplications(  
   IEnumRemoteDebugApplications**  ppeda  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppeda`  
 [out]アプリケーションを実行中の現在の一覧を格納している列挙子。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、現在の実行中のアプリケーション一覧の列挙子を返します。 デバッガー IDE では、このメソッドを使用して表示し、デバッグ目的でアプリケーションをアタッチします。  
  
## <a name="see-also"></a>関連項目  
 [IMachineDebugManagerCookie インターフェイス](../../winscript/reference/imachinedebugmanagercookie-interface.md)