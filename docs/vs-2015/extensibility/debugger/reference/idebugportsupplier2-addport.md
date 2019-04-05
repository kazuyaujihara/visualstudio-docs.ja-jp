---
title: IDebugPortSupplier2::AddPort |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugPortSupplier2::AddPort
helpviewer_keywords:
- IDebugPortSupplier2::AddPort
ms.assetid: df491161-6bf3-4fcc-b478-b9ec88ec995f
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: bf5bf281e794bde04ae0c2e86c6d27edb7edc5a7
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58976733"
---
# <a name="idebugportsupplier2addport"></a>IDebugPortSupplier2::AddPort
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

ポートを追加します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT AddPort(   
   IDebugPortRequest2* pRequest,  
   IDebugPort2**       ppPort  
);  
```  
  
```csharp  
int AddPort(   
   IDebugPortRequest2 pRequest,  
   out IDebugPort2    ppPort  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRequest`  
 [in][IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)オブジェクトを追加するポートについて説明します。  
  
 `ppPort`  
 [out]返します、 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)ポートを表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 実際には、このメソッドは、アクティブなポートのポート サプライヤーの内部一覧に追加するほか、要求されたポートを作成します。 [CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md)メソッドは時間がかかるが遅延する可能性を回避するために最初に呼び出すことができます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md)
