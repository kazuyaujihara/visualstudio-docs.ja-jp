---
title: IDebugDocument2::GetName |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocument2::GetName
helpviewer_keywords:
- IDebugDocument2::GetName
ms.assetid: 6f09ff09-b0cf-4472-8fc8-143991f0ceb1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 31eddcc07adc181e179c3f3edba669fff85fa565
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66310278"
---
# <a name="idebugdocument2getname"></a>IDebugDocument2::GetName
いくつかの形式のいずれかで、ドキュメントの名前を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetName( 
   GETNAME_TYPE gnType,
   BSTR*        pbstrFileName
);
```

```csharp
int GetName( 
   enum_GETNAME_TYPE gnType,
   out string        pbstrFileName
);
```

## <a name="parameters"></a>パラメーター
`gnType`\
[in]値、 [GETNAME_TYPE](../../../extensibility/debugger/reference/getname-type.md)返す名の種類を決定する列挙型。

`pbstrFileName`\
[out]ドキュメント名を含む文字列を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドは、タイトル、またはファイル名またはファイル名の偶数の一部として、ドキュメントの名前を返すなどのことができます。

## <a name="see-also"></a>関連項目
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)
- [GETNAME_TYPE](../../../extensibility/debugger/reference/getname-type.md)