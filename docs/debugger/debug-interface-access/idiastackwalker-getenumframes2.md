---
title: 'IDiaStackWalker:: getEnumFrames2 |Microsoft Docs'
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
ms.openlocfilehash: f6de78b5553719def2fd7ef9c6adb55e823aac34
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72741527"
---
# <a name="idiastackwalkergetenumframes2"></a>IDiaStackWalker::getEnumFrames2
特定のプラットフォームの種類のスタックフレーム列挙子を取得します。

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

からプラットフォームの種類を指定する[CV_CPU_TYPE_e enumeration](../../debugger/debug-interface-access/cv-cpu-type-e.md)列挙子の値。

 `pHelper`

からヘルパー [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)オブジェクト。

 `ppEnum`

入出力[IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)オブジェクトの一覧を含む[IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 X86 プラットフォームのみのスタックフレームリストを取得するには、 [IDiaStackWalker:: getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)メソッドを呼び出します。

## <a name="see-also"></a>関連項目
- [IDiaStackWalker](../../debugger/debug-interface-access/idiastackwalker.md)
- [CV_CPU_TYPE_e 列挙型](../../debugger/debug-interface-access/cv-cpu-type-e.md)
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
- [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)