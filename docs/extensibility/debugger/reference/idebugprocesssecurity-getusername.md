---
title: IDebugProcessSecurity::GetUserName |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a42b67eb3fd308011bf725f8dd7e24a4d9ddca6f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66311522"
---
# <a name="idebugprocesssecuritygetusername"></a>IDebugProcessSecurity::GetUserName
ポート サプライヤーからユーザー名を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetUserName(
    BSTR *pbstrUserName
);
```

```csharp
int GetUserName (
    string pbstrUserName
);
```

## <a name="parameters"></a>パラメーター
`pbstrUserName`\
[out]ユーザー名を表す文字列。

## <a name="return-value"></a>戻り値
 返します、メソッドが成功したかどうかは`S_OK`します。 それ以外の場合、エラー コードを返します。

## <a name="remarks"></a>Remarks
 `GetUserName` 表示されるユーザー名を返します、**ユーザー名**の列、**プロセスにアタッチ** ダイアログ ボックス。 表示する、**プロセスにアタッチ**ダイアログ ボックスで、をクリックして**プロセスにアタッチ**で、**ツール**でメニュー、[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]統合開発環境 (IDE)。

## <a name="see-also"></a>関連項目
- [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)