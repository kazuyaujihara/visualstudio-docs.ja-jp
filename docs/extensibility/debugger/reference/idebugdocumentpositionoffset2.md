---
title: IDebugDocumentPositionOffset2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentPositionOffset2 interface
ms.assetid: f1b05db3-50d8-453f-a72f-e68b239236a4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cf713ea542901cbde588600d40f144f0fae843e2
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56718847"
---
# <a name="idebugdocumentpositionoffset2"></a>IDebugDocumentPositionOffset2
文字のオフセットとしてソース ファイル内の位置を表します。

## <a name="syntax"></a>構文

```
IDebugDocumentPositionOffset2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 IDE によって実装され、デバッグ エンジンで使用します。

## <a name="methods"></a>メソッド
 次の表は、メソッドの`IDebugDocumentPositionOffset2`します。

|メソッド|説明|
|------------|-----------------|
|[GetRange](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2-getrange.md)|現在のドキュメントの位置の範囲を取得します。|

## <a name="remarks"></a>Remarks
 同じ情報が返されます[GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)が`char`ドキュメントの先頭からのオフセットします。 これによりは存在して、ディスクには、通常返される行と列の情報ではなく、文字の 1 次元配列と同様に、ドキュメントを表示します。

## <a name="requirements"></a>必要条件
 ヘッダー:Msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)