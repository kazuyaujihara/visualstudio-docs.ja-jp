---
title: IDebugProgram2::Attach |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::Attach
helpviewer_keywords:
- IDebugProgram2::Attach
ms.assetid: de069fbf-a565-4905-b102-f5658c55aacd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3c8cf4f3f5978744c38690681b4555f59cafd106
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56720202"
---
# <a name="idebugprogram2attach"></a>IDebugProgram2::Attach
プログラムにアタッチします。

## <a name="syntax"></a>構文

```cpp
HRESULT Attach( 
   IDebugEventCallback2* pCallback
);
```

```csharp
int Attach( 
   IDebugEventCallback2 pCallback
);
```

#### <a name="parameters"></a>パラメーター
 `pCallback`

 [in][IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)デバッグ イベント通知に使用するオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。 次の表では、いくつかの想定されるエラー コードを示します。

|[値]|説明|
|-----------|-----------------|
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|指定したプログラムがデバッガーに既に結び付けられています。|
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|アタッチ時にセキュリティ違反が発生しました。|
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|デスクトップ プログラムは、デバッガーをアタッチできません。|

## <a name="remarks"></a>Remarks
 デバッグ エンジン (DE) は、プログラムにアタッチするには、このメソッドを呼び出すことはありません。 デは、プログラムのアドレス空間で実行する場合、 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)メソッドが呼び出されます。 セッション デバッグ マネージャーの DE 実行 (SDM) のアドレス空間の場合、[アタッチ](../../../extensibility/debugger/reference/idebugengine2-attach.md)メソッドが呼び出されます。

## <a name="see-also"></a>関連項目
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
- [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)
- [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)