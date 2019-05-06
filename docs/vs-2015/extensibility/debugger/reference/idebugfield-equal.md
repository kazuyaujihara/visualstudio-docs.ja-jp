---
title: IDebugField::Equal |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugField::Equal
helpviewer_keywords:
- IDebugField::Equal method
ms.assetid: 75369fe6-ddd3-497d-80d1-2488e6100e9f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: aa630a6f2084f7ff79a9c89b685658cf694fcab9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62547313"
---
# <a name="idebugfieldequal"></a>IDebugField::Equal
このメソッドは、このフィールドに等しいかどうかを指定したフィールドを比較します。

## <a name="syntax"></a>構文

```cpp
HRESULT Equal( 
   IDebugField* pField
);
```

```csharp
int Equal(
   IDebugField pField
);
```

#### <a name="parameters"></a>パラメーター
 `pField`

 [in]この 1 と比較するフィールドです。

## <a name="return-value"></a>戻り値
 フィールドが同じ場合は、返す`S_OK`します。 フィールドが異なる場合は、返す`S_FALSE.`それ以外の場合、エラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)