---
title: 'IDiaSourceFile:: get_checksum |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_checksum method
ms.assetid: aad63a7e-4e22-44e4-8a5b-81b5174ced1e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8f4367a7862dabe248dfbe08e64c45598abe3679
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741847"
---
# <a name="idiasourcefileget_checksum"></a>IDiaSourceFile::get_checksum
チェックサムのバイト数を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_checksum ( 
   DWORD  cbData,
   DWORD* pcbData,
   BYTE   data[]
);
```

#### <a name="parameters"></a>パラメーター
 `cbData`

からデータバッファーのサイズ (バイト単位)。

 `pcbData`

入出力チェックサムのバイト数を返します。 このパラメーターを `NULL` とすることはできません。

 `data`

[入力、出力]チェックサムのバイトを格納するバッファー。 このパラメーターが `NULL` 場合、`pcbData` は必要なバイト数を返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 チェックサムバイトの生成に使用されたチェックサムアルゴリズムの種類を確認するには、 [IDiaSourceFile:: get_checksumType](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md)メソッドを呼び出します。

 チェックサムは通常、ソースファイルのイメージから生成されるため、ソースファイルの変更はチェックサムバイトの変更に反映されます。 チェックサムのバイトが、ファイルの読み込み済みイメージから生成されたチェックサムと一致しない場合は、ファイルが破損しているか、改ざんされていると見なされます。

 一般的なチェックサムは、サイズが32バイトを超えることはありませんが、がチェックサムの最大サイズであるとは限りません。 @No__t_0 パラメーターを `NULL` に設定して、チェックサムを取得するために必要なバイト数を取得します。 次に、適切なサイズのバッファーを割り当て、このメソッドを新しいバッファーでもう一度呼び出します。

## <a name="see-also"></a>関連項目
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
- [IDiaSourceFile::get_checksumType](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md)