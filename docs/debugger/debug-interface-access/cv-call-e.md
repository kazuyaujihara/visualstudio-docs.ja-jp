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
ms.openlocfilehash: ec5fea99994b891250dad85cfc43320848df98f9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62555105"
---
# <a name="cvcalle"></a>CV_call_e
関数の呼び出し規約を指定します。

> [!NOTE]
> 最も一般的な列挙値のみがここに記載されています。 完全な列挙型は cvconst.h ヘッダー ファイルで使用できます。

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
CV_CALL_NEAR_C では、ほぼ右から左へプッシュを使用して関数呼び出し規約を指定します。 呼び出し元の関数は、スタックをクリアします。

CV_CALL_NEAR_FAST 指定で、ほぼ左から右のプッシュを使用して関数呼び出し規約登録します。 呼び出された関数では、パラメーターのバイト数の合計を使用して、スタックをクリアします。

CV_CALL_NEAR_STD はほぼ標準呼び出し (右から左へプッシュ) を使用して関数呼び出し規約を指定します。

ほぼシステムを使用して関数呼び出し規約を呼び出す CV_CALL_NEAR_SYS を指定します。

CV_CALL_THISCALL 指定の関数呼び出し規約を使用して、`this`呼び出し (`this`ポインターがレジスタに渡されます)。

CV_CALL_CLRCALL 共通言語ランタイム (CLR) (とも呼ばれる呼び出し規約マネージ コード) で使用される関数呼び出し規約を指定します。

## <a name="remarks"></a>Remarks
この列挙体の値が呼び出しによって返される、 [idiasymbol::get_callingconvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)メソッド。

## <a name="requirements"></a>必要条件
ヘッダー: cvconst.h

## <a name="see-also"></a>関連項目
- [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)
