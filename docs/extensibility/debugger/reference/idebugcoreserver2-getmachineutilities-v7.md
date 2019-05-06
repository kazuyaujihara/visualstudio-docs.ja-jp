---
title: IDebugCoreServer2::GetMachineUtilities_V7 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
helpviewer_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
ms.assetid: 64c1f08f-853b-4498-9810-29791581ef2f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2929ed704d8b9642d30b9a7951a707db0635b319
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63414052"
---
# <a name="idebugcoreserver2getmachineutilitiesv7"></a>IDebugCoreServer2::GetMachineUtilities_V7
このメソッドは、サーバーのマシン ユーティリティを取得します。

> [!NOTE]
> このメソッドは廃止されています。 使用しないでください ([!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]は常に返します`E_NOTIMPL`このメソッドが呼び出された場合)。 これは歴史的な理由から保持されます。

## <a name="syntax"></a>構文

```cpp
HRESULT GetMachineUtilities_V7(
   IDebugMDMUtil2_V7** ppUtil
);
```

```csharp
int GetMachineUtilities_V7(
   out IDebugMDMUtil2_V7 ppUtil
);
```

#### <a name="parameters"></a>パラメーター
 `ppUtil`

 [out]返します、`IDebugMDMUtil2_V7`マシン ユーティリティの情報を表すインターフェイスです。

## <a name="return-value"></a>戻り値
 常に返します`E_NOTIMPL`メソッドが実装されていないことを示します。

## <a name="remarks"></a>Remarks
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 常に返します`E_NOTIMPL`場合、このメソッドが呼び出されます。

## <a name="see-also"></a>関連項目
- [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)