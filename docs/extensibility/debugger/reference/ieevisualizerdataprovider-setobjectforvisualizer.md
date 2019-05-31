---
title: IEEVisualizerDataProvider::SetObjectForVisualizer |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer
helpviewer_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer method
ms.assetid: 40dad2be-57ff-4f74-9d82-c48039c125c4
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 34fb0e8c4ae8b2b4371234e9cf09d9c21727dfdf
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350192"
---
# <a name="ieevisualizerdataprovidersetobjectforvisualizer"></a>IEEVisualizerDataProvider::SetObjectForVisualizer
このメソッドは、ビジュアライザーを表すオブジェクトを変更します。

## <a name="syntax"></a>構文

```cpp
HRESULT SetObjectForVisualizer(
   IDebugObject*  pNewObject,
   BSTR*          error,
   IDebugObject** pException
);
```

```csharp
int SetObjectForVisualizer(
   IDebugObject     pNewObject,
   out string       error,
   out IDebugObject pException
);
```

## <a name="parameters"></a>パラメーター
`pNewObject`\
[in]設定するオブジェクト。

`error`\
[out]オブジェクトを設定中にエラーがあった場合、この文字列は、エラー メッセージを保持します。

`pException`\
[out]エラーがあった場合、このオブジェクトは、例外情報を保持します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 エラー情報を返す方法を決定する、実装者の責任です。 ただし、これはことを認識する例外オブジェクトが返されたかどうかにエラーが発生しました、エラーが発生した場合、このメソッドは例外オブジェクトを返す常にする必要がありますのでのみがいくつかの呼び出し元に可能性がありますができます。 エラー文字列は、呼び出し元が作成する場合も指定するのに使用します。

## <a name="see-also"></a>関連項目
- [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)