---
title: IDiaEnumSegments |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments interface
ms.assetid: 0c9edd5e-b9ce-43e1-a791-cd4c5d16d923
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 255c55dff0dab0c7b36f5029de9e688db949a1fe
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62833429"
---
# <a name="idiaenumsegments"></a>IDiaEnumSegments
データ ソースに格納されているさまざまなセグメントを列挙します。

## <a name="syntax"></a>構文

```
IDiaEnumSegments : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
次の表は、メソッドの`IDiaEnumSegments`します。

|メソッド|説明|
|------------|-----------------|
|[IDiaEnumSegments::get__NewEnum](../../debugger/debug-interface-access/idiaenumsegments-get-newenum.md)|取得、 [IEnumVARIANT インターフェイス](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ienumvariant)この列挙子のバージョン。|
|[IDiaEnumSegments::get_Count](../../debugger/debug-interface-access/idiaenumsegments-get-count.md)|セグメントの数を取得します。|
|[IDiaEnumSegments::Item](../../debugger/debug-interface-access/idiaenumsegments-item.md)|インデックスを使用してセグメントを取得します。|
|[IDiaEnumSegments::Next](../../debugger/debug-interface-access/idiaenumsegments-next.md)|指定した列挙体シーケンス内のセグメント数を取得します。|
|[IDiaEnumSegments::Skip](../../debugger/debug-interface-access/idiaenumsegments-skip.md)|指定された数の列挙体シーケンス内のセグメントをスキップします。|
|[IDiaEnumSegments::Reset](../../debugger/debug-interface-access/idiaenumsegments-reset.md)|先頭に、列挙体シーケンスをリセットします。|
|[IDiaEnumSegments::Clone](../../debugger/debug-interface-access/idiaenumsegments-clone.md)|現在の列挙子と同じ列挙状態を格納する列挙子を作成します。|

## <a name="remarks"></a>Remarks

## <a name="notes-for-callers"></a>呼び出し元のノート
このインターフェイスを呼び出すことによって取得、`QueryInterface`メソッドを[IDiaTable](../../debugger/debug-interface-access/idiatable.md)オブジェクト。 詳細については、例を参照してください。

## <a name="example"></a>例
この例は、取得する方法を示します、`IDiaEnumSections`テーブルからのインターフェイス。 セグメントの使用のより完全な例を参照してください、 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)インターフェイス。

```C++
void ShowSegments(IDiaTable *pTable, IDiaSession *pSession)
{
    CComPtr<IDiaEnumSegments> pSegments;
    if ( SUCCEEDED( pTable->QueryInterface(
                                __uuidof( IDiaEnumSegments ),
                                (void**)&pSegments )
                  )
       )
    {
        // Do something with this enumeration
    }
}
```

## <a name="requirements"></a>必要条件
ヘッダー:Dia2.h

ライブラリ: diaguids.lib

DLL: msdia80.dll

## <a name="see-also"></a>関連項目
- [インターフェイス (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaTable](../../debugger/debug-interface-access/idiatable.md)
- [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)
