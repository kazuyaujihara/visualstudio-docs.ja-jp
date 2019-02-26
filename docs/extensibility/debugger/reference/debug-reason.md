---
title: DEBUG_REASON | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DEBUG_REASON
helpviewer_keywords:
- DEBUG_REASON enumeration
ms.assetid: ad2ee898-8648-4671-9078-d32873862346
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 03b2db1fd58af6a8b2f8a57846e7753cdbc82352
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56707264"
---
# <a name="debugreason"></a>DEBUG_REASON
デバッグ プロセスを起動した理由を指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_DEBUG_REASON {
    DEBUG_REASON_ERROR         = 0,
    DEBUG_REASON_USER_LAUNCHED = 1,
    DEBUG_REASON_USER_ATTACHED = 2,
    DEBUG_REASON_AUTO_ATTACHED = 3,
    DEBUG_REASON_CAUSALITY     = 4
};
typedef DWORD DEBUG_REASON;
```

```csharp
public enum enum_DEBUG_REASON {
    DEBUG_REASON_ERROR         = 0,
    DEBUG_REASON_USER_LAUNCHED = 1,
    DEBUG_REASON_USER_ATTACHED = 2,
    DEBUG_REASON_AUTO_ATTACHED = 3,
    DEBUG_REASON_CAUSALITY     = 4
};
```

#### <a name="parameters"></a>パラメーター
DEBUG_REASON_ERROR A 不特定のエラーが発生しました (このとして提供される既定の条件を合わせる上の理由から、もう一方のいずれの場合)。

ユーザーの要求で DEBUG_REASON_USER_LAUNCHED プロセスが開始されました。

DEBUG_REASON_USER_ATTACHED、既に実行中のプロセスは、ユーザーに関連付けられました。

DEBUG_REASON_AUTO_ATTACHED プロセスに自動的に添付起動したとき。

ために、プロセスを起動した DEBUG_REASON_CAUSALITY、*ジャスト イン タイム*(JIT) デバッグ イベント。

## <a name="remarks"></a>Remarks
返される、 [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)メソッド。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)
