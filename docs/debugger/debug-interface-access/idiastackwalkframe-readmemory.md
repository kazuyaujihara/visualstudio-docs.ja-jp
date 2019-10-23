---
title: 'IDiaStackWalkFrame:: readMemory |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame::readMemory method
ms.assetid: 7ab0b525-a5a7-4692-acad-e8c00fa9ab9a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ae1201fca1fc25cce19b40b47d6435d02d80e1b4
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741473"
---
# <a name="idiastackwalkframereadmemory"></a>IDiaStackWalkFrame::readMemory
イメージからメモリを読み取ります。

## <a name="syntax"></a>構文

```C++
HRESULT readMemory ( 
   MemoryTypeEnum type,
   ULONGLONG va,
   DWORD     cbData,
   DWORD*    pcbData,
   BYTE      data[]
);
```

#### <a name="parameters"></a>パラメーター
 `type`

からアクセスするメモリの種類を指定する[Memorytypeenum 列挙](../../debugger/debug-interface-access/memorytypeenum.md)値の1つ。

 `va`

から読み取りを開始するイメージ内の仮想アドレスの場所。

 `cbData`

からデータバッファーのサイズ (バイト単位)。

 `pcbData`

入出力返されたバイト数を返します。 @No__t_0 が `NULL` 場合、`pcbData` には、使用可能なデータの合計バイト数が含まれます。

 `data`

入出力指定された場所からデータを格納するバッファー。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)