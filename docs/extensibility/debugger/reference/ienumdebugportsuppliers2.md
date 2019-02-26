---
title: IEnumDebugPortSuppliers2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPortSuppliers2
helpviewer_keywords:
- IEnumDebugPortSuppliers2
ms.assetid: cd0a73dc-dd25-46fd-8c4f-5b011501afeb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9200c5366fb428371b633cfb0b97f72d8da8b566
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56693220"
---
# <a name="ienumdebugportsuppliers2"></a>IEnumDebugPortSuppliers2
このインターフェイスは、ポート サプライヤーを列挙します。

## <a name="syntax"></a>構文

```
IEnumDebugPortSuppliers2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 Visual Studio では、ポート サプライヤーの一覧を表すためには、このインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元のノート
 呼び出す[EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)ポート サプライヤーのリストを取得します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、メソッドの`IEnumDebugPortSuppliers2`します。

|メソッド|説明|
|------------|-----------------|
|[次へ](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-next.md)|ポート サプライヤー、列挙体シーケンス内の指定した数を取得します。|
|[Skip](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-skip.md)|ポート サプライヤー、列挙体シーケンス内の指定した数をスキップします。|
|[Reset](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-reset.md)|先頭に、列挙体シーケンスをリセットします。|
|[Clone](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-clone.md)|現在の列挙子と同じ列挙状態を格納する列挙子を作成します。|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-getcount.md)|列挙子では、ポート サプライヤーの数を取得します。|

## <a name="remarks"></a>Remarks
 デバッグ エンジンは、通常、このインターフェイスの取得には必要ありません。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)