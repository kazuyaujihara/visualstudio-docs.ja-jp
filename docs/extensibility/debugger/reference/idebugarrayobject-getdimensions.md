---
title: IDebugArrayObject::GetDimensions |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetDimensions
helpviewer_keywords:
- IDebugArrayObject::GetDimensions method
ms.assetid: 113e0aff-9028-49d6-b104-9fe7be4772d7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 60ee75454bf105f12b79d60e032549bcb84ab465
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65615237"
---
# <a name="idebugarrayobjectgetdimensions"></a>IDebugArrayObject::GetDimensions
配列の次元を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetDimensions( 
   DWORD dwCount,
   DWORD dwDimensions[]
);
```

```csharp
int GetDimensions(
   [In] uint    dwCount,
   [Out] uint[] dwDimensions
);
```

## <a name="parameters"></a>パラメーター
`dwCount`\
[in]取得するディメンションの数。

`dwDimensions`\
[入力、出力]各次元のサイズが入力する配列。 `dwCount` 最大サイズを指定します、`dwDimensions`配列。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 多次元配列の各次元のサイズが異なることができます。 たとえば、3 次元の配列を指定`myarray[3][2][6]`、3、2、および 6 でこのメソッドを返しますが、`dwDimensions`をこの順序でパラメーター。

## <a name="see-also"></a>関連項目
- [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)