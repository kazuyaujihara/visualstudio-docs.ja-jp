---
title: IDebugReference2::Compare |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReference2::Compare
helpviewer_keywords:
- IDebugReference2::Compare
ms.assetid: 3361c495-2673-4b7c-82e3-dee74e1fa58d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e5d1f1f4b31317e79c497e1b13dcd7e218ecd16b
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212992"
---
# <a name="idebugreference2compare"></a>IDebugReference2::Compare
別の 1 つの参照を比較します。 将来使用するために予約されています。

## <a name="syntax"></a>構文

```cpp
HRESULT Compare ( 
   REFERENCE_COMPARE dwCompare,
   IDebugReference2* pReference
);
```

```csharp
int Compare ( 
   enum_REFERENCE_COMPARE dwCompare,
   IDebugReference2       pReference
);
```

## <a name="parameters"></a>パラメーター
`dwCompare`\
[in]値、 [REFERENCE_COMPARE](../../../extensibility/debugger/reference/reference-compare.md)列挙操作を指定する、比較、たとえば、同じか、以下よりも、またはより大きい。

`pReference`\
[in][IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)と比較する参照を表すオブジェクト。

## <a name="return-value"></a>戻り値
 常に `E_NOTIMPL` を返します。

## <a name="see-also"></a>関連項目
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
- [REFERENCE_COMPARE](../../../extensibility/debugger/reference/reference-compare.md)