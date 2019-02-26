---
title: IDebugProgram2::WriteDump | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::WriteDump
helpviewer_keywords:
- IDebugProgram2::WriteDump
ms.assetid: 375afb8c-882d-44db-bfa7-e2c9eb555122
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: abafa1e3673a334105e8b8ec6e7957f631f000b2
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56684209"
---
# <a name="idebugprogram2writedump"></a>IDebugProgram2::WriteDump
ダンプ ファイルに書き込みます。

## <a name="syntax"></a>構文

```cpp
HRESULT WriteDump( 
   DUMPTYPE  DumpType,
   LPCOLESTR pszDumpUrl
);
```

```csharp
int WriteDump( 
   enum_DUMPTYPE  DumpType,
   string         pszDumpUrl
);
```

#### <a name="parameters"></a>パラメーター
 `DumpType`

 [in]値、 [DUMPTYPE](../../../extensibility/debugger/reference/dumptype.md)など、簡単に言えば、ダンプの種類を指定する列挙体または時間の長い。

 `pszDumpUrl`

 [in]ダンプを記述する URL です。 形式で通常、これは`file://c:\path\filename.ext`、任意の有効な URL があります。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 プログラムのダンプは、現在のスタック フレーム、スタック自体、プログラム、およびプログラムを所有するメモリ可能性がありますで実行されているスレッドの一覧に通常が含まれます。

## <a name="see-also"></a>関連項目
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)