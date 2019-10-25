---
title: 'IDiaStackWalkHelper:: readMemory |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::readMemory method
ms.assetid: e1eb90aa-49b7-476c-9e70-7e8f08994cbe
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 57afd033b2d969a4ed57dc713b2c4266e0ead632
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741361"
---
# <a name="idiastackwalkhelperreadmemory"></a>IDiaStackWalkHelper::readMemory
メモリ内の実行可能イメージからデータブロックを読み取ります。

## <a name="syntax"></a>構文

```C++
HRESULT readMemory( 
   enum MemoryTypeEnum type,
   ULONGLONG           va,
   DWORD               cbData,
   DWORD*              pcbData,
   BYTE*               pbData
);
```

#### <a name="parameters"></a>パラメーター
 `type`

から読み取るメモリの型を指定する[Memorytypeenum](../../debugger/debug-interface-access/memorytypeenum.md)列挙型の値。

 va

から読み取りを開始するイメージの仮想アドレス。

 `cbData`

からデータバッファーのサイズ (バイト単位)。

 `pcbData`

入出力実際に読み取られたバイト数を返します。 @No__t_0 が `NULL` 場合は、使用可能なデータの合計バイト数が表示されます。

 `pbData`

[入力、出力]読み取られたメモリに格納されているバッファー。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [MemoryTypeEnum 列挙型](../../debugger/debug-interface-access/memorytypeenum.md)