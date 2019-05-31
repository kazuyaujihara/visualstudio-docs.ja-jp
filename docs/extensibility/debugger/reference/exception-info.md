---
title: EXCEPTION_INFO | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- EXCEPTION_INFO
helpviewer_keywords:
- EXCEPTION_INFO structure
ms.assetid: d046957a-b97d-420b-b46b-c67cbaef709e
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 5c4fc29aee8d14e9c73dcf5665eff3ea611985d1
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66337792"
---
# <a name="exceptioninfo"></a>EXCEPTION_INFO
例外またはデバッグ中のプログラムによってスローされた実行時エラーについて説明します。

## <a name="syntax"></a>構文

```cpp
typedef struct tagEXCEPTION_INFO {
    IDebugProgram2* pProgram;
    BSTR            bstrProgramName;
    BSTR            bstrExceptionName;
    DWORD           dwCode;
    EXCEPTION_STATE dwState;
    GUID            guidType;
} EXCEPTION_INFO;
```

```csharp
public struct EXCEPTION_INFO {
    public IDebugProgram2 pProgram;
    public string         bstrProgramName;
    public string         bstrExceptionName;
    public uint           dwCode;
    public uint           dwState;
    public Guid           guidType;
};
```

## <a name="members"></a>メンバー
`pProgram`\
[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)例外が発生したプログラムを表すオブジェクト。

`bstrProgramName`\
例外が発生したプログラムの名前。

`bstrExceptionName`\
例外の名前。

`dwCode`\
例外または実行時エラーの識別コード。

`dwState`\
値、 [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md)例外の状態を定義する列挙です。

`guidType`\
GUID の言語識別子か、`guidLang`または`guidEng`します。

## <a name="remarks"></a>Remarks
この構造体がパラメーターとして渡される、 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)と[RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)メソッド。 この構造体に渡されることも、 [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)情報を格納するメソッド。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)
- [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)
- [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)
- [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)
