---
title: IDebugStackFrame2::GetLanguageInfo |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetLanguageInfo
helpviewer_keywords:
- IDebugStackFrame2::GetLanguageInfo
ms.assetid: 0e12fd92-f155-46a7-8272-cda279388cfb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 90fd7beabb14163558afe4b957d95635e91f904a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719549"
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

#### <a name="parameters"></a>パラメーター
 `pbstrLanguage`

 [out]このスタック フレームに関連付けられているメソッドを実装する言語の名前を返します。

 `pguidLanguage`

 [out]返します、`GUID`の言語。 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]言語、たとえば、次を返せること。

-   `guidVBScriptLang`

-   `guidJScriptLang`

-   `guidCPPLang`

-   `guidVBLang`

-   `guidSQLLang`

-   `guidScriptLang`

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)