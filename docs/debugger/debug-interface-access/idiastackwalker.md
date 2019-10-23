---
title: IDiaStackWalker |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker interface
ms.assetid: 4a61a22a-9cf8-4ea1-9e6e-b42f96872d40
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2366c933bf072c295b29d06ff5610bd3735c0077
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741522"
---
# <a name="idiastackwalker"></a>IDiaStackWalker
.Pdb ファイルの情報を使用してスタックウォークを実行するメソッドを提供します。

## <a name="syntax"></a>構文

```
IDiaStackWalker: IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
次の表は、`IDiaStackWalker` のメソッドを示しています。

|メソッド|説明|
|------------|-----------------|
|[IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)|X86 プラットフォームのスタックフレーム列挙子を取得します。|
|[IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)|特定のプラットフォームの種類のスタックフレーム列挙子を取得します。|

## <a name="remarks"></a>Remarks
このインターフェイスは、読み込まれたモジュールのスタックフレームの一覧を取得するために使用されます。 各メソッドには、スタックフレームの一覧を作成するために必要な情報を提供する[IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)オブジェクト (クライアントアプリケーションによって実装される) が渡されます。

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
このインターフェイスは、クラス識別子 `CLSID_DiaStackWalker` と `IID_IDiaStackWalker` のインターフェイス ID を使用して `CoCreateInstance` メソッドを呼び出すことによって取得されます。 この例は、このインターフェイスを取得する方法を示しています。

## <a name="example"></a>例
この例では、`IDiaStackWalker` インターフェイスを取得する方法を示します。

```C++

IDiaStackWalker* pStackWalker;
HRESULT hr = CoCreateInstance(CLSID_DiaStackWalker,
                              NULL,
                              CLSCTX_INPROC_SERVER,
                              IID_IDiaStackWalker,
                              (void**) &pStackWalker);
if (FAILED(hr))
{
    // Report error and exit
}
```

## <a name="requirements"></a>［要件］
ヘッダー: Dia2

ライブラリ: diaguids

DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
