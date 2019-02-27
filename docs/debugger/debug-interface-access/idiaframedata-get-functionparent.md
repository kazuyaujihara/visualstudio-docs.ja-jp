---
title: Idiaframedata::get_functionparent |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_functionParent method
ms.assetid: f00b9ab1-d4da-4818-973a-58f8f0e66769
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 20f9dac750f9ff9723e4f3669f9e9a124d728a9a
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56654127"
---
# <a name="idiaframedatagetfunctionparent"></a>IDiaFrameData::get_functionParent
外側の関数のフレーム データ インターフェイスを取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_functionParent ( 
   IDiaFrameData** pRetVal
);
```

#### <a name="parameters"></a>パラメーター
 `pRetVal`

[out]返します、 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)外側の関数のオブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)