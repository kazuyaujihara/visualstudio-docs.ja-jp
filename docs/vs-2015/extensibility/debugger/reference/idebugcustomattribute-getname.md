---
title: IDebugCustomAttribute::GetName |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttribute::GetName
helpviewer_keywords:
- IDebugCustomAttribute::GetName
ms.assetid: ba509cc5-5816-4925-a094-4c72d88c360c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4463fc4f9d321b26487e885255843a7acd945f76
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62569271"
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

#### <a name="parameters"></a>パラメーター
 `bstrName`

 [out]カスタム属性の名前を含む文字列を返します。

## <a name="return-value"></a>戻り値
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドによって返される名前付き属性を宣言するために使用するクラスの名前に対応します。 カスタム属性クラス自体の名前に対応して c# では、宣言で使用されるときにカスタム属性名から削除する"Attribute"というサフィックスとしてこの可能性がありますも一致しません。

## <a name="see-also"></a>関連項目
- [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)