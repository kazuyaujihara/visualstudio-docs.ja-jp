---
title: IDebugSymbolProvider::GetContextFromAddress |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetContextFromAddress
helpviewer_keywords:
- IDebugSymbolProvider::GetContextFromAddress method
ms.assetid: 7a27d56f-20d4-4e5c-af7b-7307d3aff0a1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 62c24adcc94b6dff82d3529658b563f811745c28
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65226543"
---
# <a name="idebugsymbolprovidergetcontextfromaddress"></a>IDebugSymbolProvider::GetContextFromAddress
このメソッドは、ドキュメントのコンテキストにデバッグ アドレスをマップします。

## <a name="syntax"></a>構文

```cpp
HRESULT GetContextFromAddress( 
   IDebugAddress*           pAddress,
   IDebugDocumentContext2** ppDocContext
);
```

```csharp
int GetContextFromAddress(
   IDebugAddress              pAddress,
   out IDebugDocumentContext2 ppDocContext
);
```

## <a name="parameters"></a>パラメーター
 `pAddress`\

 [in]デバッグ アドレスによって表される、 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)インターフェイス。

 `ppDocContext`\

 [out]によって表されるドキュメントのコンテキストを返します、 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)インターフェイス。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)
- [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)