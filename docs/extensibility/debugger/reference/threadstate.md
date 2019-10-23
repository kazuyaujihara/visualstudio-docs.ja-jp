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
ms.openlocfilehash: d86baeeab046a7e605979d3af2d6329998f796ba
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72727497"
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
 スレッドが実行中であることを示します。

 `THREADSTATE_STOPPED`\
 ブレークポイントが原因でスレッドが停止したことを示します。

 `THREADSTATE_FRESH`\
 スレッドが作成されたが、まだコードを実行していないことを示します。

 `THREADSTATE_DEAD`\
 スレッドが停止していることを示します。

 `THREADSTATE_FROZEN`\
 スレッドが固定されていることを示します (実行は実行できません)。

## <a name="remarks"></a>Remarks
 [Threadproperties](../../../extensibility/debugger/reference/threadproperties.md)構造体の `dwThreadState` フィールドに使用されます。

## <a name="requirements"></a>［要件］
 ヘッダー: msdbg. h

 名前空間: VisualStudio。

 アセンブリ: VisualStudio を実行します。

## <a name="see-also"></a>関連項目
- [列挙体](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)