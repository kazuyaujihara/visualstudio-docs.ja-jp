---
title: DataKind |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DataKind enumeration
ms.assetid: b64be708-22d6-4360-99e7-8f4e6b196de7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 31be0615fd7d1da279ecf414260af21cb8239dc8
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72745288"
---
# <a name="datakind"></a>DataKind
データ値の特定のスコープを示します。

## <a name="syntax"></a>構文

```C++
enum DataKind {
    DataIsUnknown,
    DataIsLocal,
    DataIsStaticLocal,
    DataIsParam,
    DataIsObjectPtr,
    DataIsFileStatic,
    DataIsGlobal,
    DataIsMember,
    DataIsStaticMember,
    DataIsConstant
};
```

## <a name="elements"></a>Elements
DataIsUnknown データシンボルを特定できません。

DataIsLocal データ項目はローカル変数です。

DataIsStaticLocal データ項目は静的なローカル変数です。

Dataisparc Am データ項目は、仮パラメーターです。

DataIsObjectPtr Data item はオブジェクトポインター (`this`) です。

DataIsFileStatic データ項目は、ファイルスコープの変数です。

DataIsGlobal データ項目はグローバル変数です。

DataIsMember データ項目はオブジェクトメンバー変数です。

DataIsStaticMember データ項目は、クラスの静的変数です。

DataIsConstant データ項目は定数値です。

## <a name="remarks"></a>Remarks
この列挙体の値は、 [IDiaSymbol:: get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)メソッドによって返されます。

## <a name="requirements"></a>［要件］
ヘッダー: cvconst. h

## <a name="see-also"></a>関連項目
- [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)
