---
title: IDebugModule3 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule3
helpviewer_keywords:
- IDebugModule3 interface
ms.assetid: 44f8e96e-9c59-4ffc-9a08-9c908a0e4de7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 98b506c11ef126d0179b198336e8d969c4eec267
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56721291"
---
# <a name="idebugmodule3"></a>IDebugModule3
このインターフェイスは、シンボルと JustMyCode 状態の別の場所をサポートするモジュールを表します。

## <a name="syntax"></a>構文

```
IDebugModule3 : IDebugModule2
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 デバッグ エンジン (DE) JustMyCode 状態を使用してシンボルの別の場所をサポートするためには、このインターフェイスを実装する (を参照してください、 [Visual Studio デバッガーの用語集](../../../extensibility/debugger/reference/visual-studio-debugger-glossary.md)"JustMyCode"の定義については)。

## <a name="notes-for-callers"></a>呼び出し元のノート
 呼び出し[GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)このインターフェイスを返します。 DE 送信、 [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)インターフェイスを使用してセッション デバッグ マネージャー (SDM)、[イベント](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)メソッド。 呼び出しも、 [QueryInterface](/cpp/atl/queryinterface)上、 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)インターフェイスは、このインターフェイスを返します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 メソッドだけでなく、 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)インターフェイスでは、このインターフェイスは、次のメソッドを実装します。

|メソッド|説明|
|------------|-----------------|
|[GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)|各パスの検索の結果とシンボルの検索パスの一覧を返します。|
|[LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)|読み込みを現在のモジュールのシンボルを初期化します。|
|[IsUserCode](../../../extensibility/debugger/reference/idebugmodule3-isusercode.md)|モジュールがユーザー コードを表すかどうかを指定する返しますフラグ。|
|[SetJustMyCodeState](../../../extensibility/debugger/reference/idebugmodule3-setjustmycodestate.md)|見なすかどうか、モジュールがユーザー コードかどうかを指定します。|

## <a name="remarks"></a>Remarks
 Visual Studio では、このインターフェイスの一般的な消費者です。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)
- [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)
- [GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)