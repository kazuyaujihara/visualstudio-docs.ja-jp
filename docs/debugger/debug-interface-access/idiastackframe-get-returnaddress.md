---
title: 'IDiaStackFrame:: get_returnAddress |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_returnAddress method
ms.assetid: 0df91981-919f-48ed-9c70-4121567d645b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5312eb455de8ce187bf4ae2acc2fc5b4b57a07bc
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741604"
---
# <a name="idiastackframeget_returnaddress"></a>IDiaStackFrame::get_returnAddress
フレームの返信先アドレスを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_returnAddress ( 
   ULONGLONG* pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

入出力フレームの戻り先アドレスを返します。

## <a name="return-value"></a>戻り値
 正常に終了した場合は、`S_OK` を返します。 プロパティがサポートされていない場合は `S_FALSE` を返します。 それ以外の場合はエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)