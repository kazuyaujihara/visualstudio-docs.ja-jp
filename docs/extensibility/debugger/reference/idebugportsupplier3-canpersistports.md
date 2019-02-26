---
title: IDebugPortSupplier3::CanPersistPorts |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortSupplier3::CanPersistPorts
helpviewer_keywords:
- IDebugPortSupplier3::CanPersistPorts
ms.assetid: 4127760c-e602-4e86-9232-457e382a52c7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ad31d015048d8e0732c32652141b7be060628663
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56722630"
---
# <a name="idebugportsupplier3canpersistports"></a>IDebugPortSupplier3::CanPersistPorts
このメソッドは、ポート サプライヤーが、(ディスクに書き込む) ことによってポートをデバッガーの呼び出しの間で永続化できるかどうかを判断します。

## <a name="syntax"></a>構文

```cpp
HRESULT CanPersistPorts();
```

```csharp
int CanPersistPorts();
```

#### <a name="parameters"></a>パラメーター
 なし。

## <a name="return-value"></a>戻り値
 `S_OK` ポートは、永続化する場合または`S_FALSE`をポートを保存できないことを示します。

## <a name="remarks"></a>Remarks
 ポート サプライヤーがポートを永続化できる場合が破棄されるようにする必要があり、もう一度インスタンス化されるときに再読み込みします。

## <a name="see-also"></a>関連項目
- [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)