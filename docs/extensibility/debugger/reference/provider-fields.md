---
title: PROVIDER_FIELDS |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PROVIDER_FIELDS
helpviewer_keywords:
- PROVIDER_FIELDS enumeration
ms.assetid: 39631545-2b0e-45b4-978b-d63656484b02
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 838a7dc0024e69335bf5c49c664bd491a6949d08
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "65460922"
---
# <a name="providerfields"></a>PROVIDER_FIELDS
プログラムのプロバイダーに関連付けられたプロパティを指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_PROVIDER_FIELDS {
   PFIELD_PROGRAM_NODES       = 0x01,
   PFIELD_IS_DEBUGGER_PRESENT = 0x02
};
typedef DWORD PROVIDER_FIELDS;
```

```csharp
public enum enum_PROVIDER_FIELDS {
   PFIELD_PROGRAM_NODES       = 0x01,
   PFIELD_IS_DEBUGGER_PRESENT = 0x02
};
```

## <a name="fields"></a>フィールド
 `PFIELD_PROGRAM_NODES`\
 `ProgramNodes`フィールドは有効です。

 `PFIELD_IS_DEBUGGER_PRESENT`\
 `fIsDebuggerPresent`フィールドは有効です。

## <a name="remarks"></a>Remarks
 これらの値が返されます、`Fields`のメンバー、 [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md)を構造体のどのフィールドが入力された明示的に示すために構造体。

 これらの値は、演算と組み合わせることができます`OR`します。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md)