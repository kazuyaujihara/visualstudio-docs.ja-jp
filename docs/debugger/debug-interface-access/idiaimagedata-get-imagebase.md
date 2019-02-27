---
title: Idiaimagedata::get_imagebase |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaImageData::get_imageBase method
ms.assetid: 4ba3d9e4-b205-4ee6-a41d-6996972f1f85
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: de8c333391530cd86c6fc66a8e6c36ce8cfecd5f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56623867"
---
# <a name="idiaimagedatagetimagebase"></a>IDiaImageData::get_imageBase
イメージのベースでのメモリ位置を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_imageBase ( 
   ULONGLONG* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]推奨されるイメージのベース値を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>解説
 イメージ ベースの競合によってイメージは、可能性がありますにリベースされます自動的には、未使用のメモリの場所が読み込まれるときにします。 このメソッドは、コンパイル時に、モジュールに格納された基本ヒント (推奨されるメモリの場所) を返します。

## <a name="see-also"></a>関連項目
- [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)