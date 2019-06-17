---
title: IDebugProcess3::DisableENC |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess3::DisableENC
helpviewer_keywords:
- IDebugProcess3::DisableENC
ms.assetid: cffdbdac-4d76-4aeb-aa55-5d0410db99f1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a3ee29540a11248a299d65c32cf2c8396b1fa2ef
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66314060"
---
# <a name="idebugprocess3disableenc"></a>IDebugProcess3::DisableENC
このメソッドに明示的に無効にします。 エディット コンティニュでこのプロセス (およびすべてのプログラムが含まれています)。 カスタム ポート サプライヤーが常に返す必要があります`E_NOTIMPL`します。

## <a name="syntax"></a>構文

```cpp
HRESULT DisableENC(
   EncUnavailableReason reason
);
```

```csharp
   EncUnavailableReason reason
);
```

## <a name="parameters"></a>パラメーター
`reason`\
[in]値、 [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md)列挙体。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

> [!NOTE]
> カスタム ポート サプライヤーが常に返す必要があります`E_NOTIMPL`します。

## <a name="remarks"></a>Remarks
 1 回の編集しプロセスの続行は無効です、プロセスを再起動することによってのみ再度有効にできます。

## <a name="see-also"></a>関連項目
- [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)
- [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md)