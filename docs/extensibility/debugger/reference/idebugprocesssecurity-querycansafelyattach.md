---
title: IDebugProcessSecurity::QueryCanSafelyAttach |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugProcessSecurity::QueryCanSafelyAttach
ms.assetid: 63ec1ae8-27da-4574-aa15-1c986fe9fe58
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1e718efddc90c45ced7e497a9c66c9ab3889c090
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66311435"
---
# <a name="idebugprocesssecurityquerycansafelyattach"></a>IDebugProcessSecurity::QueryCanSafelyAttach
このメソッドは、ユーザーが安全でないプロセスにアタッチする前に警告を表示するポートのサプライヤーを使用します。

## <a name="syntax"></a>構文

```cpp
HRESULT QueryCanSafelyAttach();
```

```csharp
int QueryCanSafelyAttach();
```

## <a name="return-value"></a>戻り値
 戻り値は次のとおりです。

- `S_OK`:安全ではプロセスにアタッチして、警告ダイアログ ボックスは表示されません。

- `S_FALSE`:アタッチは、セキュリティ問題と、警告ダイアログ ボックスが表示されます。

- `FAILURE`:プロセスへのアタッチに失敗します。

## <a name="see-also"></a>関連項目
- [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)