---
title: IDebugModule3::IsUserCode |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule3::IsUserCode
helpviewer_keywords:
- IDebugModule3::IsUserCode
ms.assetid: 77022946-bb8b-4114-aa81-614df6e54b13
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 39bbef1e8b831473b196d0609459b80a05e5fc2c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56718496"
---
# <a name="idebugmodule3isusercode"></a>IDebugModule3::IsUserCode
については、モジュールがかどうかにユーザー コードをどのように表すかどうかを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT IsUserCode(
   BOOL* pfUser
);
```

```csharp
int IsUserCode(
   out int pfUser
);
```

#### <a name="parameters"></a>パラメーター
 `pfUser`

 [out]0 以外の場合 (`TRUE`) モジュールでは、ユーザー コードを表している場合は 0 (`FALSE`) そうでない場合。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)