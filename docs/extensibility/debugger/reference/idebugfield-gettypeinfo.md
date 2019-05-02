---
title: IDebugField::GetTypeInfo |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugField::GetTypeInfo
helpviewer_keywords:
- IDebugField::GetTypeInfo method
ms.assetid: bb5acfa3-04c3-4088-be84-9ff8926cd16f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7b881c3b5946428bf829ca4d971bb73f814b6d45
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62919528"
---
# <a name="idebugfieldgettypeinfo"></a>IDebugField::GetTypeInfo
このメソッドは、シンボルまたは型の型に依存しない情報を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetTypeInfo( 
   TYPE_INFO* pTypeInfo
);
```

```csharp
int GetTypeInfo(
   TYPE_INFO[] pTypeInfo
);
```

#### <a name="parameters"></a>パラメーター
 `pTypeInfo`

 [out]指定された型情報を返します[TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)構造体。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 型に依存しない情報が含まれます、たとえば、AppDomain、モジュール、および記号を格納するクラス。

## <a name="see-also"></a>関連項目
- [GetType](../../../extensibility/debugger/reference/idebugfield-gettype.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)