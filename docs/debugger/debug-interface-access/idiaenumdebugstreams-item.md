---
title: 'IDiaEnumDebugStreams:: Item |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreams::Item method
ms.assetid: 6b388fe1-eabc-4720-9d59-dc09b0ceaeac
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7a07669e36d397550c28d1cc4a5de2ad300763e6
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744742"
---
# <a name="idiaenumdebugstreamsitem"></a>IDiaEnumDebugStreams::Item
インデックスまたは名前を使ってデバッグストリームを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Item (
    VARIANT                   index,
    IDiaEnumDebugStreamData** stream
);
```

#### <a name="parameters"></a>パラメーター
インデックス

から取得するデバッグストリームのインデックスまたは名前。 整数バリアントを使用する場合は、0 ~ `count`-1 の範囲で指定する必要があります。この場合 `count` は[IDiaEnumDebugStreams:: get_Count](../../debugger/debug-interface-access/idiaenumdebugstreams-get-count.md)メソッドによって返されます。

ストリーム

入出力指定されたデバッグストリームを表す[IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="example"></a>例

```C++
IDiaEnumDebugStreamData *GetStreamData(IDiaEnumDebugStreams *pStreamList,
                                       LONG whichStream)
{
    IDiaEnumDebugStreamData *pStreamData = NULL;
    if (pStreamList != NULL)
    {
        LONG numStreams = 0;
        if (pStreamList->get_count(&numStreams) == S_OK &&
            whichStream >= 0 && whichStream < numStreams)
        {
            VARIANT vIndex;
            vIndex.vt   = VT_I4;
            vIndex.lVal = whichStream;
            if (pStreamList->Item(vIndex,&pStreamData) != S_OK)
            {
                std::cerr << "Error retrieving stream " << whichStream << std::endl;
            }
        }
    }
    return(pStreamData);
}
```

## <a name="see-also"></a>関連項目
- [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)
- [IDiaEnumDebugStreams](../../debugger/debug-interface-access/idiaenumdebugstreams.md)
