---
title: 'IDiaFrameData:: get_lengthProlog |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_lengthProlog method
ms.assetid: 5f042ff1-e74e-430a-be34-d2cf1b18eff2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 00b85d1db996487d76d396d6e4df9ea557e6aae5
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743557"
---
# <a name="idiaframedataget_lengthprolog"></a>IDiaFrameData::get_lengthProlog
ブロック内のプロローグコードのバイト数を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_lengthProlog ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力プロローグコードのバイト数を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 プロローグコードは、レジスタを保持し、CPU 状態を設定し、関数のスタックを確立する命令のシーケンスです。

## <a name="see-also"></a>関連項目
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)