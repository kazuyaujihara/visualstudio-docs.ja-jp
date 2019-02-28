---
title: IDiaStackWalker::getEnumFrames2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker2::getEnumFrames2 method
ms.assetid: 73196d3f-112c-4b3a-997b-7c6b815d4afc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 35886ea0456426c30c44d5fd8e90399d4a2143ef
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56642756"
---
# <a name="idiastackwalkergetenumframes2"></a>IDiaStackWalker::getEnumFrames2
特定のプラットフォームの種類のスタック フレームの列挙子を取得します。

## <a name="syntax"></a>構文

```C++

      HRESULT getEnumFrames2( 
   enum  CV_CPU_TYPE_e    cpuid,
   IDiaStackWalkHelper*   pHelper,
   IDiaEnumStackFrames**  ppEnum
);
```

#### <a name="parameters"></a>パラメーター
 `cpuid`

[in]値、 [CV_CPU_TYPE_e 列挙型](../../debugger/debug-interface-access/cv-cpu-type-e.md)をプラットフォームの種類を指定する列挙。

 `pHelper`

[in]ヘルパー [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)オブジェクト。

 `ppEnum`

[out]返します、 [IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md)オブジェクトの一覧を含む[IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)オブジェクト。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>解説
 X86 だけのスタック フレームの一覧を取得するプラットフォームを呼び出し、 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)メソッド。

## <a name="see-also"></a>関連項目
- [IDiaStackWalker](../../debugger/debug-interface-access/idiastackwalker.md)
- [CV_CPU_TYPE_e 列挙型](../../debugger/debug-interface-access/cv-cpu-type-e.md)
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
- [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)