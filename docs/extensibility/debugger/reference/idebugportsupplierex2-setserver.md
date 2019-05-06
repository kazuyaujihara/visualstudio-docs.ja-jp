---
title: IDebugPortSupplierEx2::SetServer |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPortSupplierEx2::SetServer
ms.assetid: 0e8ef194-3a4f-4abf-8382-4607ab3005d1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ca63b2941fc0c607af93772c21ca874b3d6b9031
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62871389"
---
# <a name="idebugportsupplierex2setserver"></a>IDebugPortSupplierEx2::SetServer
ポート サプライヤーのコア サーバーを設定します。

## <a name="syntax"></a>構文

```cpp
HRESULT SetServer(
   IDebugCoreServer2* pServer
);
```

```csharp
int SetServer(
   IDebugCoreServer2 pServer
);
```

#### <a name="parameters"></a>パラメーター
 `pServer` コア サーバーのポート サプライヤーを設定します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugPortSupplierEx2](../../../extensibility/debugger/reference/idebugportsupplierex2.md)