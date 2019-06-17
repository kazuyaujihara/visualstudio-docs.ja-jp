---
title: IDebugMethodField::GetGlobalContainer |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField::GetGlobalContainer
helpviewer_keywords:
- IDebugMethodField::GetGlobalContainer method
ms.assetid: 041ac5aa-0b80-4310-b9ae-b88f8e7e0e5f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 77f3d82beab43b227dd3beb772dd41353d89b6fe
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66324186"
---
# <a name="idebugmethodfieldgetglobalcontainer"></a>IDebugMethodField::GetGlobalContainer
メソッドのグローバル コンテナーを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetGlobalContainer(
   IDebugClassField** ppClass
);
```

```csharp
int GetGlobalContainer(
   out IDebugClassField ppClass
);
```

## <a name="parameters"></a>パラメーター
`ppClass`\
[out]返します、 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)このメソッドが定義されているモジュールを表します。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 返された[IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)オブジェクトは、モジュール全体を表しており、人為的なオブジェクトは、つまり、モジュール自体には、実際のクラスはありませんで表すことができます、`IDebugClassField`さまざまなことにより、オブジェクト列挙され、検出されたモジュールの要素です。

## <a name="see-also"></a>関連項目
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)