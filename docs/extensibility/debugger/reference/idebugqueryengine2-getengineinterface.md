---
title: IDebugQueryEngine2::GetEngineInterface |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugQueryEngine2::GetEngineInterface
helpviewer_keywords:
- IDebugQueryEngine2::GetEngineInterface
ms.assetid: ed84aa98-7ec7-48f3-97ae-821090bc3664
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fbb4f5018972777e51fbaad8d06f833309f6390f
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212927"
---
# <a name="idebugqueryengine2getengineinterface"></a>IDebugQueryEngine2::GetEngineInterface
カスタム デバッグ エンジン (DE) のインターフェイスを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetEngineInterface( 
   IUnknown** ppUnk
);
```

```csharp
int GetEngineInterface( 
   out object ppUnk
);
```

## <a name="parameters"></a>パラメーター
`ppUnk`\
[out]返します、`IUnknown`オブジェクト デバッグ エンジン (DE)、および、DE に関連付けられているその他の有効なインターフェイスを照会できるを表します (たとえば[IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)または[IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md))。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドから取得されたインターフェイスを介して呼び出すセッション デバッグ マネージャーの処理を回避し、SDM 不適切な状態にまたはデバッグ中にエラーを生成する可能性がありますので、注意して、結果として得られるインターフェイスを使用する必要があります。

## <a name="see-also"></a>関連項目
- [IDebugQueryEngine2](../../../extensibility/debugger/reference/idebugqueryengine2.md)
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)