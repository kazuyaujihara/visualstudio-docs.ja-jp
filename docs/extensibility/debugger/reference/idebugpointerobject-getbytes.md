---
title: IDebugPointerObject::GetBytes |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerObject::GetBytes
helpviewer_keywords:
- IDebugPointerObject::GetBytes method
ms.assetid: e986c188-87fb-4b51-86e9-ee6a0035bdab
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7a2c93e032175ce556d5504ed8b3f57dcf619a61
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62842705"
---
# <a name="idebugpointerobjectgetbytes"></a>IDebugPointerObject::GetBytes
一連の連続するバイトとして指す値を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetBytes( 
   DWORD  dwStart,
   DWORD  dwCount,
   BYTE*  pBytes,
   DWORD* pdwBytes
);
```

```csharp
int GetBytes(
   uint       dwStart,
   uint       dwCount,
   out byte[] pBytes,
   out uint   pdwBytes
);
```

#### <a name="parameters"></a>パラメーター
 `dwStart`

 [in]指すオブジェクトの先頭からのバイト単位のオフセット。

 `dwCount`

 [in]取得するバイト数。

 `pBytes`

 [入力、出力]一連の連続するバイトの値が入力する配列が指すオブジェクトから指定されたオフセットから開始します。

 `pdwBytes`

 [out]実際に取得するバイト数を返します。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 場合、このメソッドが使用されるこれによって表されるポインター [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)プリミティブ型またはプリミティブ型 (つまり、単純なバイト シーケンスで表すことができる配列) の単純な配列を指します。

## <a name="see-also"></a>関連項目
- [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)
- [SetBytes](../../../extensibility/debugger/reference/idebugpointerobject-setbytes.md)