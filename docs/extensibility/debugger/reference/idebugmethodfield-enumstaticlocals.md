---
title: IDebugMethodField::EnumStaticLocals |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField::EnumStaticLocals
helpviewer_keywords:
- IDebugMethodField::EnumStaticLocals method
ms.assetid: e0c522c4-f759-4c32-ae87-7abcb573e77d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4fb50271801d895ca73dbbc915ff95320183d032
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56680270"
---
# <a name="idebugmethodfieldenumstaticlocals"></a>IDebugMethodField::EnumStaticLocals
メソッドの静的ローカル変数の列挙子を作成します。

## <a name="syntax"></a>構文

```cpp
HRESULT EnumStaticLocals( 
   IEnumDebugFields** ppLocals
);
```

```csharp
int EnumStaticLocals(
   out IEnumDebugFields ppLocals
);
```

#### <a name="parameters"></a>パラメーター
 `ppLocals`

 [out]返します、 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)静的ローカル変数の一覧を表すオブジェクト。 静的ローカル変数がない場合は、null 値を返します。

## <a name="return-value"></a>戻り値
 成功した場合は S_OK を返します。 または静的ローカル変数がない場合は S_FALSE を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 各要素は、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)さまざまな種類の静的ローカル変数を表すオブジェクト。 呼び出す、 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)正確に静的なローカルのオブジェクトが表す種類を決定するには、各オブジェクトのメソッド。

## <a name="see-also"></a>関連項目
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)