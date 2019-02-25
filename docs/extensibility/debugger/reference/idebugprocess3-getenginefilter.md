---
title: IDebugProcess3::GetEngineFilter |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GetEngineFilter
- IDebugProcess3::GetEngineFilter
ms.assetid: ccb7ecb0-f189-4e80-b5b2-221a095e01f5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 30dfd7b9605cf26f5cc562e6768d1f035f6b484e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56714310"
---
# <a name="idebugprocess3getenginefilter"></a>IDebugProcess3::GetEngineFilter
使用可能なデバッグ エンジンの一意の識別子の配列を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetEngineFilter(
   GUID_ARRAY *pEngineArray
);
```

```csharp
public int GetEngineFilter(
   out GUID_ARRAY[] pEngineArray
);
```

#### <a name="parameters"></a>パラメーター
 `pEngineArray`

 [out]デバッグ エンジンの一意の識別子を格納する構造体への参照。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)
- [GUID_ARRAY](../../../extensibility/debugger/reference/guid-array.md)