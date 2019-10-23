---
title: IDiaStackWalkHelper |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2 interface
ms.assetid: d66e5c84-565d-494e-8486-f91db9a34548
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 40c2b58778b2a1073b31acc7007388d8e8fe222c
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741303"
---
# <a name="idiastackwalkhelper"></a>IDiaStackWalkHelper
プログラムデバッグデータベース (.pdb) ファイルを使用して、スタックのウォークを容易にします。

## <a name="syntax"></a>構文

```

IDiaStackWalkHelper: IUnknown

```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、`IDiaStackWalkHelper` のメソッドを示しています。

|メソッド|説明|
|------------|-----------------|
|[IDiaStackWalkHelper::get_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-get-registervalue.md)|レジスタの値を取得します。|
|[IDiaStackWalkHelper::put_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-put-registervalue.md)|レジスタの値を設定します。|
|[IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)|メモリ内の実行可能イメージからデータブロックを読み取ります。|
|[IDiaStackWalkHelper::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddress.md)|指定したスタックフレーム内で、最も近い関数の戻り先アドレスを検索します。|
|[IDiaStackWalkHelper::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddressstart.md)|指定したスタックフレーム内で、指定したスタックアドレス (またはその近く) の戻りアドレスを検索します。|
|[IDiaStackWalkHelper::frameForVA](../../debugger/debug-interface-access/idiastackwalkhelper-frameforva.md)|指定した仮想アドレスを格納しているスタックフレームを取得します。|
|[IDiaStackWalkHelper::symbolForVA](../../debugger/debug-interface-access/idiastackwalkhelper-symbolforva.md)|指定した仮想アドレスを含むシンボルを取得します。 **注:** シンボルの型 `SymTagFunctionType` ( [Symtagenum 列挙](../../debugger/debug-interface-access/symtagenum.md)型の値) である必要があります。|
|[IDiaStackWalkHelper::pdataForVA](../../debugger/debug-interface-access/idiastackwalkhelper-pdataforva.md)|指定された仮想アドレスに関連付けられている PDATA データブロックを返します。|
|[IDiaStackWalkHelper::imageForVA](../../debugger/debug-interface-access/idiastackwalkhelper-imageforva.md)|実行可能ファイルのメモリ領域内のどこかに仮想アドレスが指定された場合に、実行可能ファイルの開始仮想アドレスを取得します。|

## <a name="remarks"></a>Remarks
 このインターフェイスは、プログラムの実行中にスタックフレームの一覧を作成するために実行可能ファイルに関する情報を取得するために、DIA コードによって呼び出されます。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
 クライアントアプリケーションは、このインターフェイスを実装して、プログラムの実行中にスタックをたどることをサポートします。 このインターフェイスのインスタンスは、 [IDiaStackWalker:: getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)または[IDiaStackWalker:: getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)メソッドに渡されます。

## <a name="requirements"></a>［要件］
 ヘッダー: Dia2

 ライブラリ: diaguids

 DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
- [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)
- [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)