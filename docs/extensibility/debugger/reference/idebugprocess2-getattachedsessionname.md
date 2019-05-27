---
title: IDebugProcess2::GetAttachedSessionName |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetAttachedSessionName
helpviewer_keywords:
- IDebugProcess2::GetAttachedSessionName
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 84a0969eb93fc2e95449364521662c27bf6f750d
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66202650"
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