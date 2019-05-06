---
title: IDebugModuleLoadEvent2::GetModule |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModuleLoadEvent2::GetModule
helpviewer_keywords:
- IDebugModuleLoadEvent2::GetModule
ms.assetid: c86482bb-9ce5-4e63-bbe0-969b50169424
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b17636d5f346475018e27c72562807b44b39460c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62872899"
---
# <a name="idebugmoduleloadevent2getmodule"></a>IDebugModuleLoadEvent2::GetModule
取得されているモジュール読み込みまたはアンロードします。

## <a name="syntax"></a>構文

```cpp
HRESULT GetModule( 
   IDebugModule2** pModule,
   BSTR*           pbstrDebugMessage,
   BOOL*           pbLoad
);
```

```csharp
int GetModule( 
   out IDebugModule2 pModule,
   ref string        pbstrDebugMessage,
   ref int           pbLoad
);
```

#### <a name="parameters"></a>パラメーター
 `pModule`

 [out]返します、 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)読み込みまたはアンロードされているモジュールを表すオブジェクト。

 `pbstrDebugMessage`

 [入力、出力]このイベントを説明する省略可能なメッセージが返されます。 このパラメーターが null 値の場合は、メッセージは要求されません。

 `pbLoad`

 [入力、出力]0 以外の場合 (`TRUE`) モジュールが読み込みと 0 の場合 (`FALSE`) 場合は、モジュールをアンロードしています。 このパラメーターが null 値の場合は、状態は要求されません。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md)
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)