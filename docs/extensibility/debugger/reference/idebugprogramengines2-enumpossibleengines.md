---
title: IDebugProgramEngines2::EnumPossibleEngines |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramEngines2::EnumPossibleEngines
helpviewer_keywords:
- IDebugProgramEngines2::EnumPossibleEngines
ms.assetid: 993d70a4-f6a5-4e47-a603-0b162b9fde00
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 532486c66b6feb5c397b9167e2b1cd6197513fa8
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66343398"
---
# <a name="idebugprogramengines2enumpossibleengines"></a>IDebugProgramEngines2::EnumPossibleEngines
すべての使用可能なデバッグ エンジン (DE) このプログラムをデバッグできるの Guid を返します。

## <a name="syntax"></a>構文

```cpp
HRESULT EnumPossibleEngines( 
   DWORD  celtBuffer,
   GUID*  rgguidEngines,
   DWORD* pceltEngines
);
```

```csharp
int EnumPossibleEngines( 
   uint      celtBuffer,
   GUID[]    rgguidEngines,
   ref DWORD pceltEngines
);
```

## <a name="parameters"></a>パラメーター
`celtBuffer`\
[in]返す DE Guid の数。 最大サイズを指定することも、`rgguidEngines`配列。

`rgguidEngines`\
[入力、出力]情報を格納する DE Guid の配列。

`pceltEngines`\
[out]返される DE Guid の実際の数を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。 返します [C++]`HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)`または [C#] 0x8007007A バッファーが十分な大きさでない場合。

## <a name="remarks"></a>Remarks
 エンジンの数は判断をするために 1 回このメソッドを呼び出す、`celtBuffer`パラメーター 0 に設定し、`rgguidEngines`パラメーターが null の値に設定します。 返されます。 `HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)` (0x8007007A C# の場合)、および`pceltEngines`パラメーターが必要なバッファーのサイズを返します。

## <a name="see-also"></a>関連項目
- [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)