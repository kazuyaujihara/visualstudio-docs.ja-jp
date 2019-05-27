---
title: IDebugProgramEx2::Attach |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramEx2::Attach
helpviewer_keywords:
- IDebugProgramEx2::Attach
ms.assetid: 33b22b2f-431e-4205-9441-d28a9c928c97
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 29ca7862f4882e1c1f9b3bc857c3a26095209881
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66211124"
---
# <a name="idebugprogramex2attach"></a>IDebugProgramEx2::Attach
セッションは、プログラムにアタッチします。

## <a name="syntax"></a>構文

```cpp
HRESULT Attach( 
   IDebugEventCallback2* pCallback,
   DWORD                 dwReason,
   IDebugSession2*       pSession
);
```

```csharp
int Attach( 
   IDebugEventCallback2 pCallback,
   uint                 dwReason,
   IDebugSession2       pSession
);
```

## <a name="parameters"></a>パラメーター
`pCallback`\
[in][IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)アタッチされたデバッグ エンジンにイベントを送信するコールバック関数を表すオブジェクト。

`dwReason`\
[in]値、 [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md)アタッチ操作の理由を説明する列挙体。

`pSession`\
[in]プログラムにアタッチするセッションを一意に識別する値。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外の場合はエラー コードを返します。 このメソッドが返す必要があります`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`プログラムが既にアタッチされている場合。

## <a name="remarks"></a>Remarks
 プログラムを含むポート値を使用できる`pSession`をプログラムにアタッチしようとしているセッションを確認します。 たとえば、ポートは、一度にプロセスにアタッチする 1 つだけのデバッグ セッションを許可している場合、ポートによってできます同じのセッションが既にプロセス内の他のプログラムにアタッチするかどうかを決定します。

> [!NOTE]
> インターフェイスが渡された`pSession`がクッキー、セッション デバッグ マネージャー; このプログラムへのアタッチを一意に識別する値としてのみ扱われる、指定されたインターフェイスのメソッドのいずれも機能します。

## <a name="see-also"></a>関連項目
- [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)