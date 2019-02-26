---
title: IDebugPortSupplier2::CanAddPort |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortSupplier2::CanAddPort
helpviewer_keywords:
- IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 19eb4d11ab6e67384a119f11bf070a27159c1676
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56696117"
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
ポート サプライヤーが新しいポートを追加できることを確認します。

## <a name="syntax"></a>構文

```cpp
HRESULT CanAddPort( 
   void 
);
```

```csharp
int CanAddPort();
```

## <a name="return-value"></a>戻り値
 ポートを追加できる場合を返します`S_OK`。 それ以外を返します`S_FALSE`を示すには、このポートのサプライヤーのポートは追加できません。

## <a name="remarks"></a>Remarks
 このメソッドを呼び出す前に、 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)メソッド後者の方法は、ポートに追加するには、時間のかかる操作になることがありますを作成するためです。

## <a name="see-also"></a>関連項目
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
- [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)