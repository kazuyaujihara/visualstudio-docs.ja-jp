---
title: CODE_PATH |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- CODE_PATH
helpviewer_keywords:
- CODE_PATH structure
ms.assetid: 2d4b2890-4c9d-47e1-83c0-df9c6436427f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2e9de8784f568965c1502565971af67be084f95a
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56317394"
---
# <a name="codepath"></a>CODE_PATH
メソッドまたは関数呼び出しをについて説明します。

## <a name="syntax"></a>構文

```cpp
typedef struct tagCODE_PATH { 
    BSTR                bstrName;
    IDebugCodeContext2* pCode;
} CODE_PATH;
```

```csharp
public struct CODE_PATH {
    public string            bstrName;
    public IDebugCodeContext pCode;
}
```

## <a name="members"></a>メンバー
bstrName  
コード パスの名前。

pCode  
[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)を関数にステップ インするコードのどこを識別するオブジェクト。

## <a name="remarks"></a>Remarks
この構造体は、関数にステップ インを実装するために使用されます。 [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md)デバッグ中のプログラムの現在の場所から、すべての呼び出しを返します。 この構造体は、このような 1 回の呼び出しを表します。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
[構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)  
[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)  
[EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md)
