---
title: IDebugProperty2::GetParent |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::GetParent
helpviewer_keywords:
- IDebugProperty2::GetParent
ms.assetid: 58780469-fe25-4d84-9187-67940ca0767f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 5805beed58b01c0a2a31b92008f7acdf10e4f960
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458123"
---
# <a name="idebugproperty2getparent"></a>IDebugProperty2::GetParent
プロパティの親プロパティを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetParent ( 
   IDebugProperty2** ppParent
);
```

```csharp
int GetParent ( 
   out IDebugProperty2 ppParent
);
```

## <a name="parameters"></a>パラメーター
 `ppParent`\

 [out]返します、 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)プロパティの親を表すオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`; エラー コードを返します。 返します`S_GETPARENT_NO_PARENT`親が存在しない場合。

## <a name="see-also"></a>関連項目
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)