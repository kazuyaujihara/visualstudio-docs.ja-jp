---
title: IEnumDebugProcesses2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugProcesses2
helpviewer_keywords:
- IEnumDebugProcesses2
ms.assetid: 06a1368f-10f0-44eb-af61-e388c2327111
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d3f76746c29bff7dce76c2eda97fbd1287e5906a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62914277"
---
# <a name="ienumdebugprocesses2"></a>IEnumDebugProcesses2
このインターフェイスは、デバッグ ポートで実行中のプロセスを列挙します。

## <a name="syntax"></a>構文

```
IEnumDebugProcesses : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 カスタム ポート サプライヤーは、ポートで実行されているプロセスの一覧を提供するには、このインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元のノート
 Visual Studio 呼び出し[EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)このインターフェイスを取得します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、メソッドの`IEnumDebugProcesses2`します。

|メソッド|説明|
|------------|-----------------|
|[次へ](../../../extensibility/debugger/reference/ienumdebugprocesses2-next.md)|指定された数の列挙体シーケンス内のプロセスを取得します。|
|[Skip](../../../extensibility/debugger/reference/ienumdebugprocesses2-skip.md)|指定された数の列挙体シーケンス内のプロセスをスキップします。|
|[Reset](../../../extensibility/debugger/reference/ienumdebugprocesses2-reset.md)|先頭に、列挙体シーケンスをリセットします。|
|[Clone](../../../extensibility/debugger/reference/ienumdebugprocesses2-clone.md)|現在の列挙子と同じ列挙状態を格納する列挙子を作成します。|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugprocesses2-getcount.md)|列挙子では、プロセスの数を取得します。|

## <a name="remarks"></a>Remarks
 Visual Studio では、このインターフェイスを使用して、事前設定、**プロセス**ウィンドウ。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)