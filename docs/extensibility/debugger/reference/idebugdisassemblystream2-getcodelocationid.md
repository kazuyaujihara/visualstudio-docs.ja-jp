---
title: IDebugDisassemblyStream2::GetCodeLocationId | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDisassemblyStream2::GetCodeLocationId
helpviewer_keywords:
- IDebugDisassemblyStream2::GetCodeLocationId
ms.assetid: 567adfb8-2f54-499a-a027-e4ecb82277ef
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d8169d5ec4c212cbf09ff3273f0338b3e905d721
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62875789"
---
# <a name="idebugdisassemblystream2getcodelocationid"></a>IDebugDisassemblyStream2::GetCodeLocationId
特定のコード コンテキストのコードの場所の識別子を返します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetCodeLocationId( 
   IDebugCodeContext2* pCodeContext,
   UINT64*             puCodeLocationId
);
```

```csharp
int GetCodeLocationId( 
   IDebugCodeContext2 pCodeContext,
   out ulong          puCodeLocationId
);
```

#### <a name="parameters"></a>パラメーター
 `pCodeContext`

 [in][IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)を識別子に変換するオブジェクト。

 `puCodeLocationId`

 [out]コードの場所の識別子を返します。 「解説」を参照してください。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。 返します`E_CODE_CONTEXT_OUT_OF_SCOPE`コードのコンテキストが有効な場合が範囲外です。

## <a name="remarks"></a>Remarks
 コードの場所の識別子は、逆アセンブルをサポートしているデバッグ エンジン (DE) に固有です。 この場所の識別子は、DE によって、コード内の位置を追跡するために使用し、は通常、アドレスまたは何らかのオフセット。 唯一の要件はされている場合の 1 つの場所のコードのコンテキストが別の場所のコードのコンテキストより小さい最初のコード コンテキストの対応するコードの場所 id でもは 2 つ目のコードのコンテキストのコードの場所 id よりも小さい必要があります。

 コードの場所の識別子のコードのコンテキストを取得する、 [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)メソッド。

## <a name="see-also"></a>関連項目
- [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)
- [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)
- [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)