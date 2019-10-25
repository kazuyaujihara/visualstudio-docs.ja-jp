---
title: IDiaEnumStackFrames |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumStackFrames interface
ms.assetid: 3d1e8403-c9fc-42ff-ae35-0ab9a5ed2ad7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 83e6adb3157b67b89ef2c05f59eaaf2c7084d9d8
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744018"
---
# <a name="idiaenumstackframes"></a>IDiaEnumStackFrames
使用可能なさまざまなスタックフレームを列挙します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド

|メソッド|説明|
|------------|-----------------|
|[IDiaEnumStackFrames::Next](../../debugger/debug-interface-access/idiaenumstackframes-next.md)|列挙シーケンスから指定された数のスタックフレーム要素を取得します。|
|[IDiaEnumStackFrames::Reset](../../debugger/debug-interface-access/idiaenumstackframes-reset.md)|列挙シーケンスを先頭にリセットします。|

## <a name="remarks"></a>Remarks

## <a name="notes-for-callers"></a>呼び出し元に関する注意事項
このインターフェイスを取得するには、 [IDiaStackWalker:: getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)メソッドまたは[IDiaStackWalker:: getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)メソッドを呼び出します。

## <a name="example"></a>例
この例では、`IDiaEnumStackFrames` インターフェイスを取得して使用する方法を示します。 @No__t_1 関数の実装については、 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)インターフェイスを参照してください。

```C++
void DumpStackFrames(IDiaStackWalker*     pStackWalker,
                     IDiaStackWalkHelper* pStackWalkHelper,
                     CV_CPU_TYPE_e        cpuType)
{
    if (pStackWalker != NULL && pStackWalkHelper != NULL)
    {
        CComPtr<IDiaEnumStackFrames> pEnumsFrames;
        HRESULT hr;
        hr = pStackWalker->getEnumFrames2(cpuType, pStackWalkHelper, &pEnumFrames);
        if (SUCCEEDED(hr) && pEnumFrames != NULL)
        {
            CComPtr<IDiaStackFrame> pStackFrame;
            DWORD celt = 0;

            while (pEnumFrames->Next(1, &pStackFrame, &celt) == S_OK)
            {
                PrintStackFrame(pStackFrame);
            }
            pStackFrame = NULL;
        }
    }
}
```

## <a name="requirements"></a>［要件］
ヘッダー: Dia2

ライブラリ: diaguids

DLL: msdia80

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)
- [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)
- [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)
