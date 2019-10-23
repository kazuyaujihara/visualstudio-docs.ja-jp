---
title: IDiaStackWalkHelper::p dataForVA |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::pdataByVA method
ms.assetid: fafc38fe-74dc-4726-9a51-eebf3a673d7f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8d51736a80021847881db164c9e176a010124638
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741399"
---
# <a name="idiastackwalkhelperpdataforva"></a>IDiaStackWalkHelper::pdataForVA
仮想アドレスに関連付けられている PDATA データブロックを返します。

## <a name="syntax"></a>構文

```C++
HRESULT pdataForVA( 
   ULONGLONG  va,
   DWORD      cbData,
   DWORD*     pcbData,
   BYTE*      pbData
);
```

#### <a name="parameters"></a>パラメーター
 `va`

から取得するデータの仮想アドレスを指定します。

 `cbData`

から取得するデータのサイズ (バイト単位)。

 `pcbData`

入出力取得したデータの実際のサイズをバイト単位で返します。

 `pbData`

[入力、出力]要求されたデータを格納するバッファー。 `NULL` にすることはできません。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 指定されたアドレスに PDATA がない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 コンパイル単位の PDATA ("pdata" という名前のセクション) には、関数の例外処理に関する情報が含まれています。

 呼び出し元は、返されるデータの量を認識しているため、呼び出し元は使用できるデータの量を確認する必要がありません。 したがって、このメソッドの実装では、`pbData` パラメーターが `NULL` 場合にエラーを返すことができます。

## <a name="see-also"></a>関連項目
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)