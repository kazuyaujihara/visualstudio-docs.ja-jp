---
title: IDebugProgram2::GetProgramId |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::GetProgramId
helpviewer_keywords:
- IDebugProgram2::GetProgramId
ms.assetid: 2c31c0aa-2b71-46c7-849c-356e237d26f8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a3dfec12193efda49a520a40418b93f2d4cef6b1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62870192"
---
# <a name="idebugprogram2getprogramid"></a>IDebugProgram2::GetProgramId
このプログラムの GUID を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetProgramId( 
   GUID* pguidProgramId
);
```

```csharp
int GetProgramId( 
   out Guid pguidProgramId
);
```

#### <a name="parameters"></a>パラメーター
 `pguidProgramId`

 [out]返します、`GUID`このプログラムにします。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 デバッグ エンジン (DE) は、最初に渡されたプログラム id を返す必要があります、 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)または[アタッチ](../../../extensibility/debugger/reference/idebugengine2-attach.md)メソッド。 これにより、プログラムの識別デバッガーの間でのコンポーネント。

## <a name="see-also"></a>関連項目
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)
- [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)