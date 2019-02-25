---
title: IDebugEvent2::GetAttributes |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEvent2::GetAttributes
helpviewer_keywords:
- IDebugEvent2::GetAttributes
ms.assetid: 2ac5b5fb-da17-43f7-811a-313f677e60d7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 140b47af958e8f4623dd5921aa6046926737cf38
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56677683"
---
# <a name="idebugevent2getattributes"></a>IDebugEvent2::GetAttributes
このデバッグ イベントの属性を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetAttribute( 
   DWORD* pdwAttrib
);
```

```csharp
int GetAttribute( 
   out uint pdwAttrib
);
```

#### <a name="parameters"></a>パラメーター
 `pdwAttrib`

 [out]フラグの組み合わせ、[複数](../../../extensibility/debugger/reference/eventattributes.md)列挙体。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)インターフェイスはすべてのイベントに共通です。 このメソッドは、イベントの種類を説明します。たとえば、同期または非同期のイベントし、停止イベントです。

## <a name="see-also"></a>関連項目
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md)