---
title: 'IDiaFrameData:: execute |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::execute method
ms.assetid: 7a6c7d03-1ff1-4059-bd54-5f407eeebc26
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 88c9af8293dfc6a35e5f0e42d9596494d74b10aa
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743684"
---
# <a name="idiaframedataexecute"></a>IDiaFrameData::execute
スタックアンワインドを実行し、結果をスタックウォークフレームインターフェイスに返します。

## <a name="syntax"></a>構文

```C++
HRESULT execute ( 
   IDiaStackWalkFrame* frame
);
```

#### <a name="parameters"></a>パラメーター
 `frame`

からフレームレジスタの状態を保持する[IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)オブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。 次の表に、このメソッドで使用できる戻り値を示します。

|[値]|説明|
|-----------|-----------------|
|E_DIA_INPROLOG|プロローグコードでスタックフレームを実行することはできません。|
|E_DIA_SYNTAX|フレームプログラムで解析エラーが発生しました。|
|E_DIA_FRAME_ACCESS|レジスタまたはメモリにアクセスできません。|
|E_DIA_VALUE|値の計算中にエラーが発生した (たとえば、0による除算)。|

## <a name="remarks"></a>Remarks
 このメソッドは、デバッグ中にスタックをアンワインドするために呼び出されます。 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)オブジェクトは、クライアントアプリケーションによって実装され、レジスタの更新を受け取り、`execute` メソッドによって使用されるメソッドを提供します。

## <a name="see-also"></a>関連項目
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
- [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)