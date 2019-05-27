---
title: IDebugReference2::GetDerivedMostReference |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReference2::GetDerivedMostReference
helpviewer_keywords:
- IDebugReference2::GetDerivedMostReference
ms.assetid: 07253b74-7d39-48e0-8e85-ac8dfd919f6e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4b9534c144ae08a6fa5791518fea7d463819140b
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212955"
---
# <a name="idebugreference2getderivedmostreference"></a>IDebugReference2::GetDerivedMostReference
参照の最派生参照を取得します。 将来使用するために予約されています。

## <a name="syntax"></a>構文

```cpp
HRESULT GetDerivedMostReference( 
   IDebugReference2** ppDerivedMost
);
```

```csharp
int GetDerivedMostReference( 
   out IDebugReference2 ppDerivedMost
);
```

## <a name="parameters"></a>パラメーター
`ppDerivedMost`\
[out]返します、 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)最派生プロパティを表すオブジェクト。

## <a name="return-value"></a>戻り値
 常に `E_NOTIMPL` を返します。

## <a name="remarks"></a>Remarks
 たとえば、このプロパティを実装するオブジェクトを記述する`ClassRoot`がのインスタンス化では実際には、`ClassDerived`から派生する`ClassRoot`、このメソッドから返されます、 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)オブジェクト参照を表す、`ClassDerived`オブジェクト。

## <a name="see-also"></a>関連項目
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)