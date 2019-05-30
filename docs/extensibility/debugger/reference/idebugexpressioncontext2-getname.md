---
title: IDebugExpressionContext2::GetName |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExpressionContext2::GetName
helpviewer_keywords:
- IDebugExpressionContext2::GetName
ms.assetid: c2b70d22-17af-4986-a7e3-930910367216
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d53d7f497700d4e23587927adc0c2cee37824daa
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66325876"
---
# <a name="idebugexpressioncontext2getname"></a>IDebugExpressionContext2::GetName
評価コンテキストの名前を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetName( 
   BSTR* pbstrName
);
```

```csharp
int GetName( 
   out string pbstrName
);
```

## <a name="parameters"></a>パラメーター
`pbstrName`\
[out]評価コンテキストの名前を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 名前は、この評価コンテキストの説明です。 通常この正確な評価コンテキストを参照する式エバリュエーターで解析できます。 たとえば、C++ では、名前とおりです。

```
"{ function-name, source-file-name, module-file-name }"
```

## <a name="see-also"></a>関連項目
- [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)