---
title: IDiaStackWalkHelper::p ut_registerValue |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::put_registerValue method
ms.assetid: 8f02ce54-ef59-455f-8aa6-dc26761c7aff
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 619ed78584a9fe897b19d6ac2ffd4c28838c61ab
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741367"
---
# <a name="idiastackwalkhelperput_registervalue"></a>IDiaStackWalkHelper::put_registerValue
レジスタの値を設定します。

## <a name="syntax"></a>構文

```C++
HRESULT put_registerValue ( 
   DWORD     index,
   ULONGLONG NewVal
);
```

#### <a name="parameters"></a>パラメーター
 `index`

から書き込み先のレジスタを指定する[CV_HREG_e enumeration](../../debugger/debug-interface-access/cv-hreg-e.md)列挙子の値。

 `NewVal`

から新しいレジスタ値。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 値のサイズにかかわらず、実装には、通常、レジスタが保持しているものだけを格納する必要があります。 たとえば、8ビットレジスタは、指定された値のうち最も下位の8ビットだけを保持します。

## <a name="see-also"></a>関連項目
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [CV_HREG_e 列挙型](../../debugger/debug-interface-access/cv-hreg-e.md)