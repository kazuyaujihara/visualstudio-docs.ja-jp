---
title: IDebugPropertyField::GetPropertySetter |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPropertyField::GetPropertySetter
helpviewer_keywords:
- IDebugPropertyField::GetPropertySetter method
ms.assetid: 744d76fd-2bcc-4917-a040-ce4cc714ef61
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 29772ad76df6538ec5093d2fb34427a7fa89c5ff
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345677"
---
# <a name="idebugpropertyfieldgetpropertysetter"></a>IDebugPropertyField::GetPropertySetter
プロパティを設定するメソッドを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetPropertySetter( 
   IDebugMethodField** ppField
);
```

```csharp
int GetPropertySetter(
   out IDebugMethodField ppField
);
```

## <a name="parameters"></a>パラメーター
`ppField`\
[out]返します、 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)プロパティを設定するメソッドを表すオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 プロパティを取得するメソッドを取得する、 [GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md)メソッド。

## <a name="see-also"></a>関連項目
- [IDebugPropertyField](../../../extensibility/debugger/reference/idebugpropertyfield.md)
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md)