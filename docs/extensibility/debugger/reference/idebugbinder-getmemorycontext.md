---
title: IDebugBinder::GetMemoryContext |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder::GetMemoryContext
helpviewer_keywords:
- IDebugBinder::GetMemoryContext method
ms.assetid: 801c5b60-acff-4822-b23d-e9c7bbca8a0f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b7c647f12e80adab70dd626347d52e07505e3704
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62877537"
---
# <a name="idebugbindergetmemorycontext"></a>IDebugBinder::GetMemoryContext
このメソッドでは、メモリのコンテキストにオブジェクトの場所またはメモリ アドレスのいずれかに変換します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetMemoryContext( 
   IDebugField*           pField,
   DWORD                  dwConstant,
   IDebugMemoryContext2** ppMemCxt
);
```

```csharp
int GetMemoryContext(
   IDebugField              pField,
   uint                     dwConstant,
   out IDebugMemoryContext2 ppMemCxt
);
```

#### <a name="parameters"></a>パラメーター
 `pField`

 [in][IDebugField](../../../extensibility/debugger/reference/idebugfield.md)検索するオブジェクトを記述します。 場合`NULL`を使用して`dwConstant`代わりにします。

 `dwConstant`

 [in]0x5000 などの定数のメモリ アドレス。

 `ppMemCxt`

 [out]返します、 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)オブジェクトのアドレス、またはメモリ内のアドレスを表すインターフェイスです。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)