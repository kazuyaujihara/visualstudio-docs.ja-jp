---
title: IDebugProperty2::EnumChildren |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::EnumChildren
helpviewer_keywords:
- IDebugProperty2::EnumChildren
ms.assetid: cf79f666-65d1-417c-af7c-9271bac9a267
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4aa7bbad1361053d86c59fabb58027c955856222
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66343118"
---
# <a name="idebugproperty2enumchildren"></a>IDebugProperty2::EnumChildren
プロパティの子の一覧を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT EnumChildren ( 
   DEBUGPROP_INFO_FLAGS      dwFields,
   DWORD                     dwRadix,
   REFGUID                   guidFilter,
   DBG_ATTRIB_FLAGS          dwAttribFilter,
   LPCOLESTR                 pszNameFilter,
   DWORD                     dwTimeout,
   IEnumDebugPropertyInfo2** ppEnum
);
```

```csharp
int EnumChildren ( 
   enum_DEBUGPROP_INFO_FLAGS   dwFields,
   uint                        dwRadix,
   ref Guid                    guidFilter,
   uint                        dwAttribFilter,
   string                      pszNameFilter,
   uint                        dwTimeout,
   out IEnumDebugPropertyInfo2 ppEnum
);
```

## <a name="parameters"></a>パラメーター
`dwFields`\
[in]フラグの組み合わせ、 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) 、列挙型のフィールドを指定する列挙体[DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)構造体入力します。

`dwRadix`\
[in]任意の数値情報を書式設定で使用する基数を指定します。

`guidFilter`\
[in]使用されるフィルターの GUID、`dwAttribFilter`と`pszNameFilter`パラメーターを選択する`DEBUG_PROPERTY_INFO`子が列挙されます。 たとえば、`guidFilterLocals`ローカル変数をフィルターします。

`dwAttribFilter`\
[in]フラグの組み合わせ、 [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) 、列挙するオブジェクトの種類を指定する列挙体`DBG_ATTRIB_METHOD`のこのプロパティの子になる可能性があるすべてのメソッド。 組み合わせて使用、`guidFilter`と`pszNameFilter`パラメーター。

`pszNameFilter`\
[in]使用されるフィルターの名前、`guidFilter`と`dwAttribFilter`パラメーターを選択する`DEBUG_PROPERTY_INFO`子が列挙されます。 たとえば、このパラメーターを"MyX"フィルターを"MyX"という名前のすべての子の設定

`dwTimeout`\
[in]このメソッドから戻る前に待機するミリ秒単位で最大の時間を指定します。 使用`INFINITE`を無期限に待機します。

`ppEnum`\
[out]返します、 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)子プロパティの一覧を含むオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`; エラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)
- [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)
- [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)