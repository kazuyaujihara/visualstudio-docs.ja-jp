---
title: COMPUTER_INFO |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- COMPUTER_INFO structure
ms.assetid: 943085b2-f165-462d-9a4e-2086f0cdfff4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 183c079206dd4c16a9301e370abec2f9351b1f61
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56316835"
---
# <a name="computerinfo"></a>COMPUTER_INFO
デバッガーが実行されているコンピューターをについて説明します。

## <a name="syntax"></a>構文

```cpp
typedef struct tagCOMPUTER_INFO
{
    WORD wProcessorArchitecture;
    WORD wSuiteMask;
    DWORD dwOperatingSystemVersion;
} COMPUTER_INFO;
```

```csharp
public struct COMPUTER_INFO
{
    public ushort wProcessorArchitecture;
    public ushort wSuiteMask;
    public uint dwOperatingSystemVersion;
}
```

## <a name="terms"></a>用語
wProcessorArchitecture  
マイクロプロセッサのアーキテクチャを識別します。

wSuiteMask  
スイートのマスクを識別します。

dwOperatingSystemVersion  
オペレーティング システムのバージョン番号。

## <a name="remarks"></a>Remarks
この構造体がによって返される、 [GetComputerInfo](../../../extensibility/debugger/reference/idebugwindowscomputerport2-getcomputerinfo.md)メソッド。

## <a name="requirements"></a>必要条件
ヘッダー:Msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
[構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)  
[GetComputerInfo](../../../extensibility/debugger/reference/idebugwindowscomputerport2-getcomputerinfo.md)
