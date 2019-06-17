---
title: IDebugStackFrame2::EnumProperties |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::EnumProperties
helpviewer_keywords:
- IDebugStackFrame2::EnumProperties
ms.assetid: 334bb95e-c7e0-4008-9f06-8c3999e47ee8
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ba4cf74c41d321cc03684ec6717a9eea74e9a622
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66321852"
---
# <a name="idebugstackframe2enumproperties"></a>IDebugStackFrame2::EnumProperties
ローカル変数など、スタック フレームに関連付けられているプロパティの列挙子を作成します。

## <a name="syntax"></a>構文

```cpp
HRESULT EnumProperties ( 
   DEBUGPROP_INFO_FLAGS      dwFieldSpec,
   UINT                      nRadix,
   REFIID                    refiid,
   DWORD                     dwTimeout,
   ULONG*                    pcelt,
   IEnumDebugPropertyInfo2** ppEnum
);
```

```csharp
int EnumProperties ( 
   enum_DEBUGPROP_INFO_FLAGS   dwFieldSpec,
   uint                        nRadix,
   ref Guid                    refiid,
   uint                        dwTimeout,
   out uint                    pcelt,
   out IEnumDebugPropertyInfo2 ppEnum
);
```

## <a name="parameters"></a>パラメーター
`dwFieldSpec`\
[in]フラグの組み合わせ、 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) 、列挙型のフィールドを指定する列挙体[DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)構造体入力します。

`nRadix`\
[in]任意の数値情報を書式設定で使用する基数。

`refiid`\
[in]選択に使用するフィルターの GUID [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)構造がなど、列挙`guidFilterLocals`します。

`dwTimeout`\
[in]このメソッドから戻る前に待機するミリ秒単位で最大時間。 使用`INFINITE`を無期限に待機します。

`pcelt`\
[out]列挙プロパティの数を返します。 これは、呼び出すことと同じ、 [GetCount](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md)メソッド。

`ppEnum`\
[out]返します、 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)必要なプロパティの一覧を含むオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 この方法により、選択したすべてのプロパティを単一の呼び出しで取得するため、順番に呼び出すよりも高速です、 [GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md)と[EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)メソッド。

## <a name="see-also"></a>関連項目
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)
- [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)
- [GetCount](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md)
- [GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md)
- [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)