---
title: IDebugProcess3::Step |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess3::Step
helpviewer_keywords:
- IDebugProcess3::Step
ms.assetid: 6ad9094c-27cc-4927-8a7c-1b4d97b2e436
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 296c76a386b72c3435a90e207dd76f9eeca56422
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63412951"
---
# <a name="idebugprocess3step"></a>IDebugProcess3::Step
1 つの命令またはステートメントにステップ イン プロセスをさせます。

> [!NOTE]
> このメソッドは、の代わりに使用する必要があります[手順](../../../extensibility/debugger/reference/idebugprogram2-step.md)します。

## <a name="syntax"></a>構文

```cpp
HRESULT Step(
   IDebugThread2* pThread,
   STEPKIND       sk,
   STEPUNIT       step,
);
```

```csharp
int Step(
   IDebugThread2 pThread,
   enum_STEPKIND sk,
   enum_STEPUNIT step
);
```

#### <a name="parameters"></a>パラメーター
 `pThread`

 [in][IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)ステップが実行されているスレッドを表すオブジェクト。

 `sk`

 [in]1 つ、 [STEPKIND](../../../extensibility/debugger/reference/stepkind.md)値。

 `step`

 [in]1 つ、 [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md)値。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。エラー コードを返しますそれ以外の場合。

## <a name="remarks"></a>Remarks
 任意のスレッドの同期またはスレッド間の通信が発生したとき、プロセス内の他のスレッドは、特定のスレッドがステップ実行時に実行する必要があります。

 **警告**stopping イベントまたは直接 (同期) イベントを送信しない[イベント](../../../extensibility/debugger/reference/idebugeventcallback2-event.md); この呼び出しを処理中にそれ以外の場合、デバッガーがハングします。

## <a name="see-also"></a>関連項目
- [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [STEPKIND](../../../extensibility/debugger/reference/stepkind.md)
- [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)