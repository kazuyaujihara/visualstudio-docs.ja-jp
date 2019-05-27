---
title: IDebugDocumentContext2::GetDocument |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentContext2::GetDocument
helpviewer_keywords:
- IDebugDocumentContext2::GetDocument
ms.assetid: c6d46c5d-ade8-4dc8-9862-8fc7876658c4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 43502bd66a136cc09a7deabe38ddee51a48ccbc9
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66204683"
---
# <a name="idebugdocumentcontext2getdocument"></a>IDebugDocumentContext2::GetDocument
このドキュメントのコンテキストを含むドキュメントを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetDocument( 
   IDebugDocument2** ppDocument
);
```

```csharp
int GetDocument( 
   out IDebugDocument2 ppDocument
);
```

## <a name="parameters"></a>パラメーター
`ppDocument`\
[out]返します、 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)をこのドキュメントのコンテキストを含むドキュメントを表すオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 この方法は、IDE に直接ドキュメントを提供するデバッグ エンジンです。 このメソッドが返す必要がありますそれ以外の場合、`E_NOTIMPL`します。

## <a name="see-also"></a>関連項目
- [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)