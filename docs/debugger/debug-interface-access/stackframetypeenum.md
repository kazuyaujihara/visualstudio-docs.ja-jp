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
ms.openlocfilehash: dab674576655df3b4a695d97fdfdb42df2ffa449
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227265"
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
`FrameTypeFPO`  
フレーム ポインターを指定します。FPO 情報を使用できます。

`FrameTypeTrap`  
カーネル トラップ フレーム。

`FrameTypeTSS`  
カーネル トラップ フレーム。

`FrameTypeStandard`  
標準 EBP スタック フレーム。

`FrameTypeFrameData`  
フレーム ポインターを指定します。フレーム データ情報は利用可能です。

`FrameTypeUnknown`  
すべてのデバッグ情報がないフレーム。

## <a name="remarks"></a>解説
この列挙体の値が呼び出しによって返される、 [idiastackframe::get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)メソッド。

## <a name="requirements"></a>要件
ヘッダー: cvconst.h

## <a name="see-also"></a>参照
[列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)  
[IDiaStackFrame::get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)
