---
title: AD_PROCESS_ID_TYPE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AD_PROCESS_ID_TYPE
helpviewer_keywords:
- AD_PROCESS_ID_TYPE enumeration
ms.assetid: 0aab80e9-285a-4697-94ac-c864d42a6aaa
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 405d11b0c685017d59251ba83126a73fe1a96db2
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56708967"
---
# <a name="adprocessidtype"></a>AD_PROCESS_ID_TYPE
プロセス ID を解釈する方法を指定します、 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)構造体。

## <a name="syntax"></a>構文

```cpp
enum enum_AD_PROCESS_ID {
    AD_PROCESS_ID_SYSTEM = 0,
    AD_PROCESS_ID_GUID   = 1
};
typedef DWORD AD_PROCESS_ID_TYPE;
```

```csharp
public enum enum_AD_PROCESS_ID {
    AD_PROCESS_ID_SYSTEM = 0,
    AD_PROCESS_ID_GUID   = 1
};
```

## <a name="members"></a>メンバー
AD_PROCESS_ID_SYSTEM プロセス ID は、システム識別子です。 使用して、`ProcessId.dwProcessId`のフィールド、 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)構造体。

AD_PROCESS_ID_GUID プロセス ID は GUID です。 使用して、`ProcessId.guidProcessId`のフィールド、`AD_PROCESS_ID`構造体。

## <a name="remarks"></a>Remarks
使用、`ProcessIdType`のメンバー、 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)構造に含まれているプロセス ID の種類を識別する構造体。 解釈する方法の決定、`ProcessId`共用体、構造体の。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)
