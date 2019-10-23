---
title: 'IDiaSourceFile:: get_checksumType |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_checksumType method
ms.assetid: 4c363e61-a6a9-409a-9cc0-d06eb2bee645
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c85c6ce8f03534c3ed810e530dbd12d8c6d115be
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741830"
---
# <a name="idiasourcefileget_checksumtype"></a>IDiaSourceFile::get_checksumType
チェックサムの種類を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_checksumType ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力チェックサムの種類を返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 チェックサムの種類は、チェックサムアルゴリズムにマップできる値です。 たとえば、標準の PDB ファイル形式には、通常、次のいずれかの値を指定できます。

|チェックサムの種類|CryptoAPI ラベル|説明|
|-------------------|---------------------|-----------------|
|0|\<none>|チェックサムが存在しません。|
|1|`CALG_MD5`|MD5 ハッシュアルゴリズムを使用して生成されたチェックサム。|
|2|`CALG_SHA1`|SHA1 ハッシュアルゴリズムを使用して生成されたチェックサム。|

 @No__t_0 ラベルは、`ALG_ID` 列挙体からのものです。 ハッシュアルゴリズムの詳細については、Microsoft [!INCLUDE[winsdkshort](../../debugger/debug-interface-access/includes/winsdkshort_md.md)] の `CryptoAPI` に関するセクションを参照してください。

 ソースファイルの実際のチェックサムのバイト数を取得するには、 [IDiaSourceFile:: get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md)メソッドを呼び出します。

## <a name="see-also"></a>関連項目
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
- [IDiaSourceFile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md)