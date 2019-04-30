---
title: IDebugProcessSecurity::QueryCanSafelyAttach |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugProcessSecurity::QueryCanSafelyAttach
ms.assetid: 63ec1ae8-27da-4574-aa15-1c986fe9fe58
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 891a0c200b02f8768ef68d1d87649bfd35cf59d2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62917539"
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