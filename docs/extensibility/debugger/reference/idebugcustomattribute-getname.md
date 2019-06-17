---
title: IDebugCustomAttribute::GetName |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttribute::GetName
helpviewer_keywords:
- IDebugCustomAttribute::GetName
ms.assetid: ba509cc5-5816-4925-a094-4c72d88c360c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 3ed7abc9682d0a9f56c50fe7510ed3f276a6bf5a
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66315206"
---
# <a name="idebugcustomattributegetname"></a>IDebugCustomAttribute::GetName
カスタム属性の名前を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetName( 
   BSTR* bstrName
);
```

```csharp
int GetName(
   out string bstrName
);
```

## <a name="parameters"></a>パラメーター
`bstrName`\
[out]カスタム属性の名前を含む文字列を返します。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドによって返される名前付き属性を宣言するために使用するクラスの名前に対応します。 カスタム属性クラス自体の名前に対応して c# では、宣言で使用されるときにカスタム属性名から削除する"Attribute"というサフィックスとしてこの可能性がありますも一致しません。

## <a name="see-also"></a>関連項目
- [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)