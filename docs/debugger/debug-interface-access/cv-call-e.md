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
ms.openlocfilehash: 9d8c11e84a514739049a044a12ae482f7b2d9929
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56316187"
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
CV_CALL_NEAR_C  
ほぼ右から左へプッシュを使用して関数呼び出し規約を指定します。 呼び出し元の関数は、スタックをクリアします。

CV_CALL_NEAR_FAST  
ほぼ左から右プッシュを使用してレジスタと共に関数呼び出し規約を指定します。 呼び出された関数では、パラメーターのバイト数の合計を使用して、スタックをクリアします。

CV_CALL_NEAR_STD  
Near の標準的な呼び出し (右から左へプッシュ) を使用して関数呼び出し規約を指定します。

CV_CALL_NEAR_SYS  
ほぼシステム コールを使用して関数呼び出し規約を指定します。

CV_CALL_THISCALL  
使用して関数呼び出し規約を指定します。`this`呼び出し (`this`ポインターがレジスタに渡されます)。

CV_CALL_CLRCALL  
共通言語ランタイム (CLR) (とも呼ばれる呼び出し規約マネージ コード) で使用される関数呼び出し規約を指定します。

## <a name="remarks"></a>解説
この列挙体の値が呼び出しによって返される、 [idiasymbol::get_callingconvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)メソッド。

## <a name="requirements"></a>要件
ヘッダー: cvconst.h

## <a name="see-also"></a>関連項目
[列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)  
[IDiaSymbol::get_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)
