---
title: IDebugDocumentContext2::Seek |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentContext2::Seek
helpviewer_keywords:
- IDebugDocumentContext2::Seek
ms.assetid: 71501356-8a82-4d36-b354-6625bdd2baa0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fbba9b1208ced73c24fbb7050bb4d7e2f8266d52
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66201172"
---
# <a name="idebugdocumentcontext2seek"></a>IDebugDocumentContext2::Seek
ステートメントまたは行の番号を指定して、ドキュメントのコンテキストに移動します。

## <a name="syntax"></a>構文

```cpp
HRESULT Seek( 
   int                      nCount,
   IDebugDocumentContext2** ppDocContext
);
```

```cpp
int Seek( 
   int                        nCount,
   out IDebugDocumentContext2 ppDocContext
);
```

## <a name="parameters"></a>パラメーター
`nCount`\
[in]ステートメントまたは順方向に移動、ドキュメントのコンテキストに応じて行の数。

`ppDocContext`\
[out]新しいを返します[IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)新しい位置を持つオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)