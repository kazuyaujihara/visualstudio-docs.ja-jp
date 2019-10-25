---
title: CV_call_e |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_call_e enumeration
ms.assetid: f230560b-4243-432d-8f19-46df112043b9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5deb59d4bbee06e505ba10bf1d4f08b1b06aa62d
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745353"
---
# <a name="cv_call_e"></a>CV_call_e
関数の呼び出し規約を指定します。

> [!NOTE]
> 最も一般的な列挙値のみがここに記載されています。 完全な列挙体は、cvconst .h ヘッダーファイルで使用できます。

## <a name="syntax"></a>構文

```C++
typedef enum CV_call_e {
    CV_CALL_NEAR_C    = 0x00,
    CV_CALL_NEAR_FAST = 0x04,
    CV_CALL_NEAR_STD  = 0x07,
    CV_CALL_NEAR_SYS  = 0x09,
    CV_CALL_THISCALL  = 0x0b,
    CV_CALL_CLRCALL   = 0x16
} CV_call_e;
```

## <a name="elements"></a>Elements
CV_CALL_NEAR_C は、右から左方向のプッシュを使用して関数呼び出し規約を指定します。 呼び出し元の関数は、スタックをクリアします。

CV_CALL_NEAR_FAST は、レジスタを使用して、左から右へのほぼ右のプッシュを使用して、関数呼び出し規約を指定します。 呼び出された関数は、パラメーターバイトの合計を使用してスタックをクリアします。

CV_CALL_NEAR_STD は、ほぼ標準の呼び出し (右から左方向のプッシュ) を使用して関数呼び出し規約を指定します。

CV_CALL_NEAR_SYS は、NEAR システム呼び出しを使用して関数呼び出し規約を指定します。

CV_CALL_THISCALL は `this` 呼び出し (レジスタに渡された `this` ポインター) を使用して関数呼び出し規約を指定します。

CV_CALL_CLRCALL は、共通言語ランタイム (CLR) によって使用される関数呼び出し規約を指定します (マネージコードの呼び出し規約とも呼ばれます)。

## <a name="remarks"></a>Remarks
この列挙体の値は、 [IDiaSymbol:: get_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)メソッドの呼び出しによって返されます。

## <a name="requirements"></a>［要件］
ヘッダー: cvconst. h

## <a name="see-also"></a>関連項目
- [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)
