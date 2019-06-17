---
title: IDebugProcess2::GetAttachedSessionName |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetAttachedSessionName
helpviewer_keywords:
- IDebugProcess2::GetAttachedSessionName
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1d14e76e576aaf3e467ab24083d445c9d9fc5214
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353161"
---
# <a name="idebugprocess2getattachedsessionname"></a>IDebugProcess2::GetAttachedSessionName
このプロセスがデバッグ セッションの名前を取得します。 IDE では、特定のコンピューターの特定のプロセスのデバッグは、ユーザーにこの情報を表示できます。

> [!NOTE]
> このメソッドは廃止され、その実装を常に返します`E_NOTIMPL`します。

## <a name="syntax"></a>構文

```
HRESULT GetAttachedSessionName(
   BSTR* pbstrSessionName
);
```

## <a name="parameters"></a>パラメーター
`pbstrSessionName`\

## <a name="return-value"></a>戻り値
 このメソッドは常に返します`E_NOTIMPL`します。

## <a name="see-also"></a>関連項目
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)