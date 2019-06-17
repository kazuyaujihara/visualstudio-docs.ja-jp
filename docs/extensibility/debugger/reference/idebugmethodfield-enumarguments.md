---
title: IDebugMethodField::EnumArguments |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField::EnumArguments
helpviewer_keywords:
- IDebugMethodField::EnumArguments method
ms.assetid: 3ab55488-2437-4ff6-a9ae-78ea6d7b23a8
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 0f0c5f95267948b6fb2c1cab1a7d79a2e62b9e3c
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66346785"
---
# <a name="idebugmethodfieldenumarguments"></a>IDebugMethodField::EnumArguments
メソッドの呼び出しに必要な各引数の型の列挙子を作成します。

## <a name="syntax"></a>構文

```cpp
HRESULT EnumArguments( 
   IEnumDebugFields** ppParams
);
```

```csharp
int EnumArguments(
   out IEnumDebugFields ppParams
);
```

## <a name="parameters"></a>パラメーター
`ppParams`\
[out]返します、 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)引数の型のリストを表すオブジェクト。 引数がない場合は、null 値を返します。

## <a name="return-value"></a>戻り値
 成功した場合は S_OK を返します。 または引数がない場合は S_FALSE を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 各要素は、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)各パラメーターの型を表すオブジェクト。 呼び出す、 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)メソッドは各パラメーターの型に関する情報を取得します。

 型とパラメーターの名前が必要な場合を呼び出して、 [EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)メソッド。

## <a name="see-also"></a>関連項目
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)