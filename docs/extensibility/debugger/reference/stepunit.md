---
title: STEPUNIT |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- STEPUNIT
helpviewer_keywords:
- STEPUNIT enumeration
ms.assetid: cb8441f2-f744-4e73-acfe-ae8542df9649
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4115a1d7e01558f2991503200a76dabbf81993bc
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "65460996"
---
# <a name="stepunit"></a>STEPUNIT
ステップ実行するための増加単位を指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_STEPUNIT { 
   STEP_STATEMENT   = 0,
   STEP_LINE        = 1,
   STEP_INSTRUCTION = 2
};
typedef DWORD STEPUNIT;
```

```csharp
enum enum_STEPUNIT { 
   STEP_STATEMENT   = 0,
   STEP_LINE        = 1,
   STEP_INSTRUCTION = 2
};
```

## <a name="fields"></a>フィールド
 `STEP_STATEMENT`\
 ステートメントで手順を実行します。

 `STEP_LINE`\
 行をステップ実行します。

 `STEP_INSTRUCTION`\
 命令で手順を実行します。

## <a name="remarks"></a>Remarks
 引数として渡される、[手順](../../../extensibility/debugger/reference/idebugprocess3-step.md)メソッド。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [Step](../../../extensibility/debugger/reference/idebugprocess3-step.md)