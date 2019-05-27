---
title: IDebugGenericParamField::GetIndex |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugGenericParamField::GetIndex
ms.assetid: 8e0bdb26-1247-44d9-8d80-ec6e35187fb4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 53b671ad653ee9a4806f9090d4c192cb460f77d2
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66211837"
---
# <a name="idebuggenericparamfieldgetindex"></a>IDebugGenericParamField::GetIndex
このジェネリック パラメーターのインデックスを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetIndex(
    DWORD* pIndex
);
```

```csharp
int GetIndex(
    out uint pIndex
);
```

## <a name="parameters"></a>パラメーター
`pIndex`\
[out]このジェネリック パラメーターのインデックス値。

## <a name="return-value"></a>戻り値
成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
たとえば、Dictionary(K,V)、K はインデックス 0、V はインデックス 1。

## <a name="example"></a>例
次の例では、このメソッドを実装する方法を示しています、 **CDebugGenericParamFieldType**を公開するオブジェクト、 [IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md)インターフェイス。

```cpp
HRESULT CDebugGenericParamFieldType::GetIndex(DWORD* pIndex)
{
    HRESULT hr = S_OK;

    METHOD_ENTRY( CDebugGenericParamFieldType::GetIndex );

    IfFalseGo(pIndex, E_INVALIDARG );
    IfFailGo( this->LoadProps() );
    *pIndex = m_index;

Error:

    METHOD_EXIT( CDebugGenericParamFieldType::GetIndex, hr );
    return hr;
}
```

## <a name="see-also"></a>関連項目
- [IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md)
