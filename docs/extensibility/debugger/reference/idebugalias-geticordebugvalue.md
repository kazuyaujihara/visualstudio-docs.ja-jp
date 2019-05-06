---
title: IDebugAlias::GetICorDebugValue |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAlias::GetICorDebugValue
helpviewer_keywords:
- IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 59506af5ad48bd18c454f4c59367921eed1e679a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62924078"
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

#### <a name="parameters"></a>パラメーター
 `ppUnk`

 [out]`IUnknown`このエイリアスに関連付けられている値を表すインターフェイスです。 このインターフェイスを照会できます、`ICorDebugValue`インターフェイス。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドは、管理対象の値のみに適用されます (、`ICorDebugValue`インターフェイスでは、[!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)]で定義されていると、 [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] SDK では cordebug.idl ファイル)。

## <a name="see-also"></a>関連項目
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)