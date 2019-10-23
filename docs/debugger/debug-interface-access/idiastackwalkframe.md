---
title: IDiaStackWalkFrame |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame interface
ms.assetid: 42d82845-d6f6-4846-9ecd-9dd169216077
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5b2657127726e387e81a5b28c639abbaa5399019
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741437"
---
# <a name="idiastackwalkframe"></a>IDiaStackWalkFrame
[IDiaFrameData:: execute](../../debugger/debug-interface-access/idiaframedata-execute.md)メソッドの呼び出し間でスタックコンテキストを保持します。

## <a name="syntax"></a>構文

```
IDiaStackWalkFrame : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、`IDiaStackWalkFrame` のメソッドを示しています。

|メソッド|説明|
|------------|-----------------|
|[IDiaStackWalkFrame::get_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-get-registervalue.md)|レジスタの値を取得します。|
|[IDiaStackWalkFrame::put_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-put-registervalue.md)|レジスタの値を設定します。|
|[IDiaStackWalkFrame::readMemory](../../debugger/debug-interface-access/idiastackwalkframe-readmemory.md)|イメージからメモリを読み取ります。|
|[IDiaStackWalkFrame::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddress.md)|指定したスタックフレーム内で、最も近い関数の戻り先アドレスを検索します。|
|[IDiaStackWalkFrame::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddressstart.md)|指定したスタックフレーム内で、指定したアドレスまたはその近くの戻りアドレスを検索します。|

## <a name="remarks"></a>Remarks
 このインターフェイスは、プログラムの実行中に、レジスタの読み取りと書き込みと、メモリへのアクセス、およびリターンアドレスの検索のために使用されます。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 クライアントアプリケーションは、このインターフェイスを実装し、インターフェイスのインスタンスを[IDiaFrameData:: execute](../../debugger/debug-interface-access/idiaframedata-execute.md)メソッドに渡します。 このインターフェイスの同じインスタンスを再度使用して、`execute` メソッドの各呼び出し時にレジスタの状態を維持します。 また、`execute` メソッドは、このインターフェイスを使用して、戻り先アドレスを決定します。

## <a name="requirements"></a>［要件］
 ヘッダー: Dia2

 ライブラリ: diaguids

 DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md)