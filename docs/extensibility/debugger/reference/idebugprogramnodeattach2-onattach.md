---
title: IDebugProgramNodeAttach2::OnAttach |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramNodeAttach2::OnAttach
helpviewer_keywords:
- IDebugProgramNodeAttach2::OnAttach
ms.assetid: 5fe52761-a508-4ab5-abdb-334fb6590334
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c30ad0216944ec7c5c707b17df585a689a42b396
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49936141"
---
# <a name="idebugprogramnodeattach2onattach"></a>IDebugProgramNodeAttach2::OnAttach
関連付けられているプログラムにアタッチするか、アタッチ プロセスの遅延、[アタッチ](../../../extensibility/debugger/reference/idebugengine2-attach.md)メソッド。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT OnAttach(  
   [in] REFGUID guidProgramId  
);  
```  
  
```csharp  
int OnAttach(  
   ref Guid guidProgramId  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 `guidProgramId`  
 [in]`GUID`に関連付けられているプログラムを割り当てます。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`します。 返します`S_FALSE`場合、[アタッチ](../../../extensibility/debugger/reference/idebugengine2-attach.md)メソッドを呼び出すことはできません。 それ以外の場合はエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドを呼び出すアタッチ中に、前に、[アタッチ](../../../extensibility/debugger/reference/idebugengine2-attach.md)メソッドが呼び出されます。 `OnAttach`メソッド、attach プロセス自体を実行できます (この場合は、このメソッドを返します`S_FALSE`) にアタッチ プロセスを延期または、`IDebugEngine2::Attach`メソッド (、`OnAttach`メソッドを返します。 `S_OK`)。 いずれの場合、`OnAttach`メソッドを設定できます、`GUID`をデバッグ中のプログラムの指定された`GUID`します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [添付](../../../extensibility/debugger/reference/idebugengine2-attach.md)