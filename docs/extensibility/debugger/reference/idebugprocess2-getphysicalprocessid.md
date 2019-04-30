---
title: IDebugProcess2::GetPhysicalProcessId | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetPhysicalProcessId
helpviewer_keywords:
- IDebugProcess2::GetPhysicalProcessId
ms.assetid: 77da6e10-75af-4308-97dd-c44416ca52d7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2f8a822932479cab7b62be52951c83c6d016fcc2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62870892"
---
# <a name="idebugprocess2getphysicalprocessid"></a>IDebugProcess2::GetPhysicalProcessId
システム プロセス識別子を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetPhysicalProcessId(
   AD_PROCESS_ID* pdwProcessId
);
```

```csharp
int GetPhysicalProcessId(
   AD_PROCESS_ID[] pdwProcessId
);
```

#### <a name="parameters"></a>パラメーター
 `pdwProcessId`

 [out][AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)構造をシステム プロセス識別子情報が入力されます。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)