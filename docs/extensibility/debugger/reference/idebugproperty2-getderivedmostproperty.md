---
title: IDebugProperty2::GetDerivedMostProperty |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProperty2::GetDerivedMostProperty
helpviewer_keywords:
- IDebugProperty2::GetDerivedMostProperty
ms.assetid: cc86b461-62d1-4340-8209-c65037fd8b02
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 58713b63728678ccab55435eb05b1cbb1c8920fc
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49929882"
---
# <a name="idebugproperty2getderivedmostproperty"></a>IDebugProperty2::GetDerivedMostProperty
プロパティの最派生プロパティを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetDerivedMostProperty (   
   IDebugProperty2** ppDerivedMost  
);  
```  
  
```csharp  
int GetDerivedMostProperty (   
   out IDebugProperty2 ppDerivedMost  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppDerivedMost`  
 [out]返します、 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)最派生プロパティを表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`; エラー コードを返します。 返します`S_GETDERIVEDMOST_NO_DERIVED_MOST`を取得する最派生プロパティが存在しない場合。  
  
## <a name="remarks"></a>Remarks  
 たとえば、このプロパティを実装するオブジェクトを記述する`ClassRoot`がのインスタンス化では実際には、`ClassDerived`から派生する`ClassRoot`、このメソッドから返されます、 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)オブジェクト記述する、`ClassDerived`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)