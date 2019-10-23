---
title: 'IDiaEnumTables:: Item |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Item method
ms.assetid: d65ab262-10c6-48ce-95a3-b5e4cb2c85af
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bf2d6b14f17d42a128e59446e27bfc251de40d17
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743747"
---
# <a name="idiaenumtablesitem"></a>IDiaEnumTables::Item
インデックスまたは名前を使ってテーブルを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT Item ( 
   VARIANT     index,
   IDiaTable** table
);
```

#### <a name="parameters"></a>パラメーター
 `index`

から取得する[IDiaTable](../../debugger/debug-interface-access/idiatable.md)のインデックスまたは名前。 整数バリアントを使用する場合は、0 ~ `count`-1 の範囲で指定する必要があります。この場合 `count` は[IDiaEnumTables:: get_Count](../../debugger/debug-interface-access/idiaenumtables-get-count.md)メソッドによって返されます。

 `table`

入出力目的のテーブルを表す[IDiaTable](../../debugger/debug-interface-access/idiatable.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 文字列バリアントが指定されている場合、文字列は特定のテーブルに名前を指定します。 名前は、[定数 (Debug Interface Access SDK)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)で定義されているテーブル名のいずれかである必要があります。

## <a name="example"></a>例

```C++
VARIANT var;
var.vt = VT_BSTR;
var.bstrVal = SysAllocString(DiaTable_Symbols );
IDiaTable* pTable;
pEnumTables->Item( var, &pTable );
```

## <a name="see-also"></a>関連項目
- [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)
- [IDiaTable](../../debugger/debug-interface-access/idiatable.md)
- [IDiaEnumTables::get_Count](../../debugger/debug-interface-access/idiaenumtables-get-count.md)
- [定数 (Debug Interface Access SDK)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)