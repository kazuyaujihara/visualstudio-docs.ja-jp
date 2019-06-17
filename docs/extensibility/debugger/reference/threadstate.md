---
title: THREADSTATE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- THREADSTATE
helpviewer_keywords:
- THREADSTATE enumeration
ms.assetid: 62efdd7c-25b1-4fd3-9d06-ac1830a418a9
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 50f487b3d44fc1b871b00348ec28693b36c49685
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66316140"
---
# <a name="threadstate"></a>THREADSTATE
スレッドの状態を指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_THREADSTATE { 
   THREADSTATE_RUNNING = 0x0001,
   THREADSTATE_STOPPED = 0x0002,
   THREADSTATE_FRESH   = 0x0003,
   THREADSTATE_DEAD    = 0x0004,
   THREADSTATE_FROZEN  = 0x0005
};
typedef DWORD THREADSTATE;
```

```csharp
public enum enum_THREADSTATE { 
   THREADSTATE_RUNNING = 0x0001,
   THREADSTATE_STOPPED = 0x0002,
   THREADSTATE_FRESH   = 0x0003,
   THREADSTATE_DEAD    = 0x0004,
   THREADSTATE_FROZEN  = 0x0005
};
```

## <a name="fields"></a>フィールド
 `THREADSTATE_RUNNING`\
 スレッドが実行されていることを示します。

 `THREADSTATE_STOPPED`\
 ブレークポイントのため、スレッドが停止していることを示します。

 `THREADSTATE_FRESH`\
 スレッドが作成されたらは、コードがまだ実行されていないことを示します。

 `THREADSTATE_DEAD`\
 スレッドが実行されないことを示します。

 `THREADSTATE_FROZEN`\
 スレッドが固定されていることを示します (の実行を実行できません)。

## <a name="remarks"></a>Remarks
 使用、`dwThreadState`のフィールド、 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)構造体。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)