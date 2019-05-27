---
title: IEnumDebugFrameInfo2::Clone |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugFrameInfo2::Clone
helpviewer_keywords:
- IEnumDebugFrameInfo2::Clone
ms.assetid: cdd10489-1772-47e3-815f-a6cfd32a3c60
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 7bfd96f1a52fe908e414b16bb7bd003b459059d4
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66208006"
---
# <a name="ienumdebugframeinfo2clone"></a>IEnumDebugFrameInfo2::Clone
個別のオブジェクトとして現在の列挙体のコピーを返します。

## <a name="syntax"></a>構文

```cpp
HRESULT Clone(
   IEnumDebugFrameInfo2** ppEnum
);
```

```csharp
int Clone(
   out IEnumDebugFrameInfo2 ppEnum
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
- [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)