---
title: IDebugAlias::GetICorDebugValue |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAlias::GetICorDebugValue
helpviewer_keywords:
- IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f8ef27f9af5626b716339281c010c62c2515fb8b
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2019
ms.locfileid: "66746842"
---
# <a name="idebugaliasgeticordebugvalue"></a>IDebugAlias::GetICorDebugValue
このエイリアスに関連付けられている値を表すマネージ コード インターフェイスを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetICorDebugValue(
   IUnknown** ppUnk
);
```

```csharp
int GetICorDebugValue(
   out object ppUnk
);
```

## <a name="parameters"></a>パラメーター
`ppUnk`\
[out]`IUnknown`このエイリアスに関連付けられている値を表すインターフェイスです。 このインターフェイスを照会できます、`ICorDebugValue`インターフェイス。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドは、管理対象の値のみに適用されます (、`ICorDebugValue`はインターフェイスを .NET Framework で使用でき、cordebug.idl ファイルに .NET Framework SDK で定義されている)。

## <a name="see-also"></a>関連項目
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)