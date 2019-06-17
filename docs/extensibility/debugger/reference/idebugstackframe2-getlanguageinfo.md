---
title: IDebugStackFrame2::GetLanguageInfo |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetLanguageInfo
helpviewer_keywords:
- IDebugStackFrame2::GetLanguageInfo
ms.assetid: 0e12fd92-f155-46a7-8272-cda279388cfb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d220e3c1d9e7b5879d12ed31f6a3374e6c481fe3
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66352145"
---
# <a name="idebugstackframe2getlanguageinfo"></a>IDebugStackFrame2::GetLanguageInfo
このスタック フレームに関連付けられている言語を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetLanguageInfo ( 
   BSTR* pbstrLanguage,
   GUID* pguidLanguage
);
```

```csharp
int GetLanguageInfo ( 
   ref string pbstrLanguage,
   ref Guid   pguidLanguage
);
```

## <a name="parameters"></a>パラメーター
`pbstrLanguage`\
[out]このスタック フレームに関連付けられているメソッドを実装する言語の名前を返します。

`pguidLanguage`\
[out]返します、`GUID`の言語。 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]言語、たとえば、次を返せること。

-   `guidVBScriptLang`\

-   `guidJScriptLang`\

-   `guidCPPLang`\

-   `guidVBLang`\

-   `guidSQLLang`\

-   `guidScriptLang`\

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)