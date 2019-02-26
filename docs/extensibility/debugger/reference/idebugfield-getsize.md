---
title: IDebugField::GetSize |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugField::GetSize
helpviewer_keywords:
- IDebugField::GetSize method
ms.assetid: 73329924-3751-4f44-af54-5986b7943374
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fa10836b91306a99629e80b6869880f018878c38
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56707992"
---
# <a name="idebugfieldgetsize"></a>IDebugField::GetSize
このメソッドは、(バイト単位)、フィールドのサイズを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetSize( 
   DWORD* pdwSize
);
```

```csharp
int GetSize(
   out uint pdwSize
);
```

#### <a name="parameters"></a>パラメーター
 `pdwSize`

 [out]サイズを返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 すべてのフィールドの型であるし、すべての種類、サイズに設定します。 たとえば、バイトの種類をフィールドには、1 バイトのサイズがあります。

## <a name="see-also"></a>関連項目
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)