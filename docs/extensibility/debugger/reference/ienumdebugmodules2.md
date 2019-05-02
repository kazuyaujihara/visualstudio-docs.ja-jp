---
title: IEnumDebugModules2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugModules2
helpviewer_keywords:
- IEnumDebugModules2
ms.assetid: 4fe28074-a960-41ad-b74d-b57f04c0c0ad
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c92a7f47f088a92a898e6cc5acbffe3522d9fec4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62914501"
---
# <a name="ienumdebugmodules2"></a>IEnumDebugModules2
このインターフェイスは、モジュールの一覧を列挙します。

## <a name="syntax"></a>構文

```
IEnumDebugModules2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 デバッグ エンジン (DE) は、プログラムに読み込まれたモジュールの一覧を表すためには、このインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元のノート
 Visual Studio 呼び出し[EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)このインターフェイスを取得します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、メソッドの`IEnumDebugModules2`します。

|メソッド|説明|
|------------|-----------------|
|[次へ](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md)|指定された数の列挙体シーケンス内のモジュールを取得します。|
|[Skip](../../../extensibility/debugger/reference/ienumdebugmodules2-skip.md)|指定された数の列挙体シーケンス内のモジュールをスキップします。|
|[Reset](../../../extensibility/debugger/reference/ienumdebugmodules2-reset.md)|先頭に、列挙体シーケンスをリセットします。|
|[Clone](../../../extensibility/debugger/reference/ienumdebugmodules2-clone.md)|現在の列挙子と同じ列挙状態を格納する列挙子を作成します。|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugmodules2-getcount.md)|モジュールの数を取得します。|

## <a name="remarks"></a>Remarks
 Visual Studio では、このインターフェイスを使用して、更新するには、主に、**モジュール**ウィンドウ。

 Visual Studio でのデバッグの目的では、プログラムはコード命令をそのモジュールの境界を越えることができますの論理シーケンス、1 つのモジュールの一覧の必要性[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)インターフェイス。 一覧の最初のモジュールには、通常、関連付けられたプログラムの最初のエントリ ポイントが含まれています。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)