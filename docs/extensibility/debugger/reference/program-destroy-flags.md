---
title: PROGRAM_DESTROY_FLAGS |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- PROGRAM_DESTROY_FLAGS enumeration
ms.assetid: be00d4a3-d5b8-4159-b632-64577f534883
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e232570edd4fcca95089324e30f3cbd725bdb9f8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62865074"
---
# <a name="programdestroyflags"></a>PROGRAM_DESTROY_FLAGS
有効な列挙値は、プログラムのフラグを破棄します。

## <a name="syntax"></a>構文

```cpp
enum enum_PPROGRAM_DESTROY_FLAGS
{
   PROGRAM_DESTROY_CONTINUE_DEBUGGING = 0x1
};
typedef DWORD PROGRAM_DESTROY_FLAGS;
```

```csharp
public enum enum_PPROGRAM_DESTROY_FLAGS
{
   PROGRAM_DESTROY_CONTINUE_DEBUGGING = 0x1
};
```

## <a name="terms"></a>用語
 PROGRAM_DESTROY_CONTINUE_DEBUGGING 破棄、プログラムしますが、デバッグを続行します。

## <a name="remarks"></a>Remarks
 列挙体は、によって返される、 [GetFlags](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md)メソッド。

## <a name="requirements"></a>必要条件
 ヘッダー:Msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetFlags](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md)