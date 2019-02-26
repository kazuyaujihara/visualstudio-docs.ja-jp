---
title: IDebugObject::GetValue |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::GetValue
helpviewer_keywords:
- IDebugObject::GetValue method
ms.assetid: eec6051e-8ecb-49fa-bdd4-dd786f211692
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8d8b55fed250b94fc02c9810eca17ec0934bf81e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56690735"
---
# <a name="idebugobjectgetvalue"></a>IDebugObject::GetValue
連続した一連のバイトとしてオブジェクトの値を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetValue( 
   BYTE* pValue,
   UINT  nSize
);
```

```csharp
int GetValue(
   ref byte[] pValue,
   uint nSize
);
```

#### <a name="parameters"></a>パラメーター
 `pValue`

 [入力、出力]入力が連続する一連のオブジェクトの値を表すバイト配列。

 `nSize`

 [in]フェッチするバイトの最大数。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 呼び出すことでフェッチできる値のバイトの合計数を取得、 [GetSize](../../../extensibility/debugger/reference/idebugobject-getsize.md)メソッド。

## <a name="see-also"></a>関連項目
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)