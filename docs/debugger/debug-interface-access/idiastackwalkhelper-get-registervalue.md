---
title: IDiaStackWalkHelper::get_registerValue |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::get_registerValue method
ms.assetid: 46ac5eee-73a3-44a1-8635-6c58ba193cb6
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 275941aaf3a1eb2cab6554b18c6d9aa66605121a
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56613038"
---
# <a name="idiastackwalkhelpergetregistervalue"></a>IDiaStackWalkHelper::get_registerValue
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

[in]値、 [CV_HREG_e 列挙型](../../debugger/debug-interface-access/cv-hreg-e.md)から値を取得する登録を指定する列挙体。

 `pRetVal`

[out]レジスタの現在の値を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>解説
 サイズに関係なく、`pRetVal`パラメーター、実装がのみ何レジスタは、通常は保持を格納する必要があります。 など、8 ビット レジスタのみ、最下位 8 ビットの指定された値を保持します。 この 8 ビット値は、このメソッドから返されるときに 64 ビットに拡張されます。

## <a name="see-also"></a>参照
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [CV_HREG_e 列挙型](../../debugger/debug-interface-access/cv-hreg-e.md)