---
title: 'IDiaStackWalkFrame:: get_registerValue |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame::get_registerValue method
ms.assetid: ca3c20a9-934a-4b2c-a7f6-7d06e8611ff2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d5d1010cf9231e4777c8aef8de4a71d23937974e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741505"
---
# <a name="idiastackwalkframeget_registervalue"></a>IDiaStackWalkFrame::get_registerValue
レジスタの値を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_registerValue ( 
   DWORD      index,
   ULONGLONG* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `index`

から値を取得するレジスタを指定する[CV_HREG_e enumeration](../../debugger/debug-interface-access/cv-hreg-e.md)列挙子の値。

 `pRetVal`

入出力レジスタの現在の値を返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)
- [CV_HREG_e 列挙型](../../debugger/debug-interface-access/cv-hreg-e.md)