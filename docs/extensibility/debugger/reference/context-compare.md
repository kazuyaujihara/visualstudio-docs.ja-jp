---
title: CONTEXT_COMPARE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CONTEXT_COMPARE
helpviewer_keywords:
- CONTEXT_COMPARE enumeration
ms.assetid: 701ed61c-a320-4c20-a335-0b840024abc0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 21628bda9dc0437672b0b755bb64f1c882b0acbf
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689175"
---
# <a name="contextcompare"></a>CONTEXT_COMPARE
メモリの 2 つのコンテキストを比較するための条件を指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_CONTEXT_COMPARE {
    CONTEXT_EQUAL                 = 0x0001,
    CONTEXT_LESS_THAN             = 0x0002,
    CONTEXT_GREATER_THAN          = 0x0003,
    CONTEXT_LESS_THAN_OR_EQUAL    = 0x0004,
    CONTEXT_GREATER_THAN_OR_EQUAL = 0x0005,
    CONTEXT_SAME_SCOPE            = 0x0006,
    CONTEXT_SAME_FUNCTION         = 0x0007,
    CONTEXT_SAME_MODULE           = 0x0008,
    CONTEXT_SAME_PROCESS          = 0x0009
};
typedef DWORD CONTEXT_COMPARE;
```

```csharp
public enum enum_CONTEXT_COMPARE {
    CONTEXT_EQUAL                 = 0x0001,
    CONTEXT_LESS_THAN             = 0x0002,
    CONTEXT_GREATER_THAN          = 0x0003,
    CONTEXT_LESS_THAN_OR_EQUAL    = 0x0004,
    CONTEXT_GREATER_THAN_OR_EQUAL = 0x0005,
    CONTEXT_SAME_SCOPE            = 0x0006,
    CONTEXT_SAME_FUNCTION         = 0x0007,
    CONTEXT_SAME_MODULE           = 0x0008,
    CONTEXT_SAME_PROCESS          = 0x0009
};
```

## <a name="members"></a>メンバー
CONTEXT_EQUAL は、ターゲット メモリのコンテキストに相当するリスト内の最初のメモリのコンテキストを検索します。

CONTEXT_LESS_THAN は、ターゲット メモリのコンテキストよりも小さいリスト内の最初のメモリのコンテキストを検索します。

CONTEXT_GREATER_THAN は、ターゲット メモリのコンテキストよりも大きいリスト内の最初のメモリのコンテキストを検索します。

CONTEXT_LESS_THAN_OR_EQUAL は、ターゲット メモリ コンテキスト未満であるリストで最初のメモリのコンテキストを検索します。

CONTEXT_GREATER_THAN_OR_EQUAL は、ターゲット メモリ コンテキスト以上であるリストで最初のメモリのコンテキストを検索します。

CONTEXT_SAME_SCOPE は、ターゲット メモリのコンテキストと同じスコープ内にある一覧で最初のメモリのコンテキストを検索します。

CONTEXT_SAME_FUNCTION は、ターゲット メモリの範囲と同じ関数内にある一覧で最初のメモリのコンテキストを検索します。

CONTEXT_SAME_MODULE は、ターゲット メモリのコンテキストと同じモジュール内にある一覧で最初のメモリのコンテキストを検索します。

CONTEXT_SAME_PROCESS は、ターゲット メモリのコンテキストと同じプロセス内にある一覧で最初のメモリのコンテキストを検索します。

## <a name="remarks"></a>Remarks
引数として渡される、[比較](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)メソッド。

これらの値は、指定した比較条件を満たすリスト内の最初のメモリのコンテキストの検索に使用されます。 メモリ コンテキストがを介してに対して自身を比較するメモリのコンテキストの一覧を指定された、`IDebugMemoryContext2::Compare`メソッド。 比較演算子の一覧で最初のメモリ コンテキスト`true`が返されます。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [Compare](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)
