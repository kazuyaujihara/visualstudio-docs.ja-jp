---
title: IDebugProgram2::GetENCUpdate |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::GetENCUpdate
helpviewer_keywords:
- IDebugProgram2::GetENCUpdate
ms.assetid: 9832aac8-6320-4fd8-91dd-2a0852febb00
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2de204f3d95147d3250e570fa785ecccf68b4634
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63412774"
---
# <a name="idebugprogram2getencupdate"></a>IDebugProgram2::GetENCUpdate
このメソッドは、このプログラムの編集と続行 (ENC) の更新プログラムを取得します。 カスタム デバッグ エンジンは常に返します`E_NOTIMPL`します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetENCUpdate( 
   IUnknown** ppUpdate
);
```

```csharp
int GetENCUpdate(
   out object ppUpdate
);
```

#### <a name="parameters"></a>パラメーター
 `ppUpdate`

 [out]このプログラムを更新するために使用する内部インターフェイスを返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

> [!NOTE]
> カスタム デバッグ エンジンは常に返す必要があります`E_NOTIMPL`します。

## <a name="see-also"></a>関連項目
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)