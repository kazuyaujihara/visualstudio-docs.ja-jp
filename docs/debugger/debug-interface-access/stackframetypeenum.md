---
title: StackFrameTypeEnum |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- StackFrameTypeEnum enumeration
ms.assetid: 61e40163-eee0-4c1f-af47-cef3771bdc41
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 44f715c4f74d9b120b324e2d68417a24c9b42684
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62854831"
---
# <a name="stackframetypeenum"></a>StackFrameTypeEnum
スタック フレームの種類を指定します。

## <a name="syntax"></a>構文

```C++
enum StackFrameTypeEnum {
    FrameTypeFPO,
    FrameTypeTrap,
    FrameTypeTSS,
    FrameTypeStandard,
    FrameTypeFrameData,
    FrameTypeUnknown = -1
};
```

## <a name="elements"></a>Elements
`FrameTypeFPO` フレーム ポインターを指定します。FPO 情報を使用できます。

`FrameTypeTrap` カーネル トラップ フレーム。

`FrameTypeTSS` カーネル トラップ フレーム。

`FrameTypeStandard` 標準 EBP スタック フレーム。

`FrameTypeFrameData` フレーム ポインターを指定します。フレーム データ情報は利用可能です。

`FrameTypeUnknown` すべてのデバッグ情報がないフレーム。

## <a name="remarks"></a>Remarks
この列挙体の値が呼び出しによって返される、 [idiastackframe::get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)メソッド。

## <a name="requirements"></a>必要条件
ヘッダー: cvconst.h

## <a name="see-also"></a>関連項目
- [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaStackFrame::get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)
