---
title: IDebugProgramEngines2::SetEngine |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramEngines2::SetEngine
helpviewer_keywords:
- IDebugProgramEngines2::SetEngine
ms.assetid: c05857ee-89cf-455e-8f1e-300cce4a2eab
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7541971da9420b0527b7c9885f1421b8c2ce0075
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68182170"
---
# <a name="idebugprogramengines2setengine"></a>IDebugProgramEngines2::SetEngine
プログラムまたはプログラムのノードにするデバッグ エンジンを使用してこのプログラムをデバッグするには、(DE) を指示します。

## <a name="syntax"></a>構文

```cpp
HRESULT SetEngine( 
   REFGUID guidEngine
);
```

```csharp
int SetEngine( 
   ref Guid guidEngine
);
```

#### <a name="parameters"></a>パラメーター
 `guidEngine`

 [in]デの GUID です。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)