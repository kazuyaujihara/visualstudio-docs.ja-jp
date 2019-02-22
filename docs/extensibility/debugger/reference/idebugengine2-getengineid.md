---
title: IDebugEngine2::GetEngineID |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::GetEngineID
helpviewer_keywords:
- IDebugEngine2::GetEngineID
ms.assetid: 0d5674c8-a9b9-4b72-8211-d2d68695775a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 09863abc81d3f4f1a5e4e541c9e0019d30156b67
ms.sourcegitcommit: 845442e2b515c3ca1e4e47b46cc1cef4df4f08d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "56449634"
---
# <a name="idebugengine2getengineid"></a>IDebugEngine2::GetEngineID
デバッグ エンジン (DE) の GUID を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetEngineID(
    GUID* pguidEngine
);
```

```csharp
int GetEngineID(
    out Guid pguidEngine
);
```

#### <a name="parameters"></a>パラメーター
`pguidEngine`  
[out]デの GUID を返します。

## <a name="return-value"></a>戻り値
成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
一般的な Guid の例としては、 `guidScriptEng`、 `guidNativeEng`、または`guidSQLEng`します。 新しいデバッグ エンジンでは、識別のため、独自の GUID を作成します。

## <a name="example"></a>例
次の例は、単純なは、このメソッドを実装する方法を示しています。`CEngine`を実装するオブジェクト、 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)インターフェイス。

```cpp
HRESULT CEngine::GetEngineId(GUID *pguidEngine) {
    if (pguidEngine) {
        // Set pguidEngine to guidBatEng, as defined in the Batdbg.idl file.
        // Other languages would require their own guidDifferentEngine to be
        //defined in the Batdbg.idl file.
        *pguidEngine = guidBatEng;
        return NOERROR; // This is typically S_OK.
    } else {
        return E_INVALIDARG;
    }
}
```

## <a name="see-also"></a>関連項目
[IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
