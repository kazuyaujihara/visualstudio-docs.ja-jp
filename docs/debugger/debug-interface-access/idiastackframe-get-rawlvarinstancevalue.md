---
title: 'IDiaStackFrame:: get_rawLVarInstanceValue |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_rawLVarInstanceValue method
ms.assetid: ce526259-85a6-475b-9274-0b3a21d95db2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0b1118517988f6a790cd4f6732eba3bc8a9fc25a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741634"
---
# <a name="idiastackframeget_rawlvarinstancevalue"></a>IDiaStackFrame::get_rawLVarInstanceValue
このメソッドは、指定されたローカル変数の値を生のバイトとして取得します。

## <a name="syntax"></a>構文

```C++
HRESULT get_rawLVarInstanceValue(
   IDiaLVarInstance* pInstance,
   DWORD             cbDataMax,
   DWORD*            pcbData,
   BYTE*             pbData
);
```

#### <a name="parameters"></a>パラメーター
 `pInstance`

から値を取得するローカル変数のインスタンスを表す `IDiaLVarInstance` オブジェクト。

 `cbDataMax`

から@No__t_0 が指すバッファー内の最大バイト数。 最大8バイト (`sizeof(ULONGLONG)`) を指定できます。

 `pcbData`

入出力バッファーに格納されている実際のバイト数を返します。

 `pbData`

入出力データを格納するバッファー。 これは `NULL` にすることはできません。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)