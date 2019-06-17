---
title: IDebugCoreServer3::DiagnoseWebDebuggingError |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
helpviewer_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
ms.assetid: 8c4570ca-ae55-42f2-bbaa-8d8e75d2fa19
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 52b6d634da7cda9c7b90b8cd4f7d93e7accc033d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66317794"
---
# <a name="idebugcoreserver3diagnosewebdebuggingerror"></a>IDebugCoreServer3::DiagnoseWebDebuggingError
Auto-attach できなかった理由を特定する試行が失敗しました。

## <a name="syntax"></a>構文

```cpp
HRESULT DiagnoseWebDebuggingError(
   LPCWSTR pszUrl
);
```

```csharp
int DiagnoseWebDebuggingError(
   string pszUrl
);
```

## <a name="parameters"></a>パラメーター
`pszUrl`\
[in]使用されていません。null 値に常に設定する必要があります。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。 次に、その他の一般的なリターン コードを示します。

|コード|説明|
|----------|-----------------|
|`S_WEBDBG_UNABLE_TO_DIAGNOSE`|デバッグを開始するリモート サーバーが失敗した理由を判断できません。|
|`S_WEBDBG_DEBUG_VERB_BLOCKED`|十分なアクセス許可の可能性があるため、リモート サーバーでデバッグすることはできません、DEBUG の動詞が有効になっていませんか。|
|`E_WEBDBG_DEBUG_VERB_BLOCKED`|Web サーバーがロックダウンされているし、デバッグを有効にするには、必要な DEBUG 動詞をブロックします。|

## <a name="see-also"></a>関連項目
- [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)