---
title: MACHINE_INFO |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- MACHINE_INFO
helpviewer_keywords:
- MACHINE_INFO structure
ms.assetid: e7564ff2-00b5-4750-8fd5-dc1029a16912
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e548552b5acda6a3334b6d7df90b2aeab80c2e77
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49847228"
---
# <a name="machineinfo"></a>MACHINE_INFO
特定のコンピューターについて説明します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
typedef struct tagMACHINE_INFO {   
   MACHINE_INFO_FIELDS Fields;  
   BSTR                bstrName;  
   MACHINE_INFO_FLAGS  Flags;  
} MACHINE_INFO;  
```  
  
```csharp  
public struct MACHINE_INFO {   
   public uint   Fields;  
   public string bstrName;  
   public uint   Flags;  
};  
```  
  
## <a name="members"></a>メンバー  
 `Fields`  
 フラグの組み合わせ、 [MACHINE_INFO_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md)構造体のフィールドが初期化されるかを指定する列挙体。  
  
 `bstrName`  
 コンピューター名。 呼び出しに相当[GetMachineName](../../../extensibility/debugger/reference/idebugcoreserver2-getmachinename.md)します。  
  
 `Flags`  
 フラグの組み合わせ、 [MACHINE_INFO_FLAGS](../../../extensibility/debugger/reference/machine-info-flags.md)マシン属性を説明する列挙体。  
  
## <a name="remarks"></a>Remarks  
 この構造体が呼び出しによって返される、 [GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md)メソッド。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [MACHINE_INFO_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md)   
 [GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md)