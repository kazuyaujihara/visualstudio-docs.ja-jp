---
title: IEnumCodePaths2::Clone |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumCodePaths2::Clone
helpviewer_keywords:
- IEnumCodePaths2::Clone
ms.assetid: 9d5c6bc6-7e72-4f1b-801c-7192458f3ba8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 85a3df07e782c022ab1e40ad311b10e7a3f7ae96
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66209867"
---
# <a name="ienumcodepaths2clone"></a>IEnumCodePaths2::Clone
個別のオブジェクトとして現在の列挙体のコピーを返します。

## <a name="syntax"></a>構文

```cpp
HRESULT Clone(
   IEnumCodePaths2** ppEnum
);
```

```csharp
int Clone(
   out IEnumCodePaths2 ppEnum
);
```

## <a name="parameters"></a>パラメーター
`ppEnum`\
[out]個別のオブジェクトとして、この列挙体のコピーを返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 列挙体のコピーは、このメソッドが呼び出されたとき、元と同じ状態が。 ただし、コピーのと、元の状態は別であり、個別に変更することができます。

## <a name="see-also"></a>関連項目
- [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)