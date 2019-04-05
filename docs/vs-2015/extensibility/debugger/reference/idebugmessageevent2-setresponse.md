---
title: IDebugMessageEvent2::SetResponse |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugMessageEvent2::SetResponse
helpviewer_keywords:
- IDebugMessageEvent2::SetResponse method
- SetResponse method
ms.assetid: 2a5e318d-3225-4abd-83f1-28323baff6c0
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0d73bcab1f2bec1b1ce856362967a937dfea9a0f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58975549"
---
# <a name="idebugmessageevent2setresponse"></a>IDebugMessageEvent2::SetResponse
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

メッセージ ボックスから存在する場合、応答を設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT SetResponse(   
   DWORD dwResponse  
);  
```  
  
```csharp  
int SetResponse(   
   uint dwResponse  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwResponse`  
 [in]Win32 の規則を使用して、応答を指定します`MessageBox`関数。 参照してください、 [AfxMessageBox](http://msdn.microsoft.com/library/d66d0328-cdcc-48f6-96a4-badf089099c8)詳細については、関数。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)   
 [AfxMessageBox](http://msdn.microsoft.com/library/d66d0328-cdcc-48f6-96a4-badf089099c8)
