---
title: IDiaSectionContrib::get_relocationsCrc | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_relocationsCrc method
ms.assetid: 8c29c91a-062d-4566-a9b7-49251036a15a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4b8602cfefbd414561ebfbaee979e6af5711b879
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742542"
---
# <a name="idiasectioncontribget_relocationscrc"></a>IDiaSectionContrib::get_relocationsCrc
セクションの再配置情報の巡回冗長検査 (CRC) を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_relocationsCrc ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力セクションの再配置情報の CRC を返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 このプロパティがサポートされていない場合は、`S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)