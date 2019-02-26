---
title: IDebugEnumField::GetValueFromStringCaseInsensitive |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEnumField::GetValueFromStringCaseInsensitive
helpviewer_keywords:
- IDebugEnumField::GetValueFromStringCaseInsensitive method
ms.assetid: ef95b38e-d9b2-4fb5-a166-7c2e14641dc7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: db1efb094694863f4deda8a7c2f380077f952a1a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56685315"
---
# <a name="idebugenumfieldgetvaluefromstringcaseinsensitive"></a>IDebugEnumField::GetValueFromStringCaseInsensitive
このメソッドでは、検索を使用して、列挙定数の名前に関連付けられた値を返します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetValueFromStringCaseInsensitive(
   LPCOLESTR  pszValue,
   ULONGLONG* pvalue
);
```

```csharp
int GetValueFromStringCaseInsensitive(
   string    pszValue,
   out ulong pValue
);
```

#### <a name="parameters"></a>パラメーター
 `pszValue`

 [in]値を取得する対象の名前を指定する文字列。 C++、ワイド文字の文字列は、このことに注意してください。

 `pValue`

 [out]関連付けられている数値を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`名前列挙型、またはエラー コードの一部でない場合は、します。

## <a name="remarks"></a>Remarks
 このメソッドは大文字です。 (たとえば、C++ の名前が大文字小文字を区別などの言語) で大文字と小文字が必要に応じて、使用して[GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)します。

## <a name="see-also"></a>関連項目
- [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)
- [GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)