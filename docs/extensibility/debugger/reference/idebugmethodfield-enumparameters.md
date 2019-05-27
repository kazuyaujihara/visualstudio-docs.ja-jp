---
title: IDebugMethodField::EnumParameters |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField::EnumParameters
helpviewer_keywords:
- IDebugMethodField::EnumParameters method
ms.assetid: d77b1197-deb6-4144-8d1b-8b09949ccfac
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a9bc7a2049f98c06b83907061cfbee063c810baf
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66210329"
---
# <a name="idebugmethodfieldenumparameters"></a>IDebugMethodField::EnumParameters
メソッドのパラメーターの列挙子を作成します。

## <a name="syntax"></a>構文

```cpp
HRESULT EnumParameters( 
   IEnumDebugFields** ppParams
);
```

```csharp
int EnumParameters(
   out IEnumDebugFields ppParams
);
```

## <a name="parameters"></a>パラメーター
`ppParams`\
[out]返します、 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)メソッドにパラメーターの一覧を表すオブジェクト。 それ以外の場合、パラメーターがない場合に null 値を返します。

## <a name="return-value"></a>戻り値
 成功した場合は S_OK を返します。 またはパラメーターがない場合は S_FALSE を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 各要素は、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)さまざまな種類のパラメーターを表すオブジェクト。 呼び出す、 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)正確にパラメーターのオブジェクトが表す種類を決定するには、各オブジェクトのメソッド。

 パラメーターには、その変数の名前とその型の両方が含まれています。 クラスのメソッドの最初のパラメーターは、通常"this"ポインターです。

 パラメーターの型は、必要な場合のみを呼び出す、 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)メソッド。

## <a name="see-also"></a>関連項目
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)