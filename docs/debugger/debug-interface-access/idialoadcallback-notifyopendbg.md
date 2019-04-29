---
title: Idialoadcallback::notifyopendbg |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback::NotifyOpenDBG method
ms.assetid: dbc4dcf0-4ace-4dce-9790-0fdaf3a23d3b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 97ca8b06a480d2fddb2002a0b9a19f878caa58f5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62828605"
---
# <a name="idialoadcallbacknotifyopendbg"></a>IDiaLoadCallback::NotifyOpenDBG
候補 .dbg ファイルが開かれたときに呼び出されます。

## <a name="syntax"></a>構文

```C++
HRESULT NotifyOpenDBG ( 
   LPCOLESTR dbgPath,
   HRESULT   resultCode
);
```

#### <a name="parameters"></a>パラメーター
 `dbgPath`

[in].Dbg ファイルの完全パス。

 `resultCode`

[in]成功を示すコード (`S_OK`) またはこのファイルに適用されると、負荷の失敗。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。 リターン コードは通常は無視されます。

## <a name="see-also"></a>関連項目
- [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)