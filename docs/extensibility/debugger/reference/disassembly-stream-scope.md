---
title: DISASSEMBLY_STREAM_SCOPE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DISASSEMBLY_STREAM_SCOPE
helpviewer_keywords:
- DISASSEMBLY_STREAM_SCOPE enumeration
ms.assetid: 43e2b364-cbbe-4755-a7e6-a03f3054c965
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 446b0eec7593457ed2cd384eb9a6bca383094e62
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56684495"
---
# <a name="disassemblystreamscope"></a>DISASSEMBLY_STREAM_SCOPE
[逆アセンブル] ストリームのスコープを指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_DISASSEMBLY_STREAM_SCOPE {
    DSS_HUGE     = 0x10000000,
    DSS_FUNCTION = 0x0001,
    DSS_MODULE   = (DSS_HUGE) | 0x0002,
    DSS_ALL      = (DSS_HUGE) | 0x0003
};
typedef DWORD DISASSEMBLY_STREAM_SCOPE;
```

```csharp
public enum enum_DISASSEMBLY_STREAM_SCOPE {
    DSS_HUGE     = 0x10000000,
    DSS_FUNCTION = 0x0001,
    DSS_MODULE   = (DSS_HUGE) | 0x0002,
    DSS_ALL      = (DSS_HUGE) | 0x0003
};
```

## <a name="members"></a>メンバー
DSS_HUGE 指定、コードのコンテキストを逆アセンブル クライアントよりも多い出力を生成する通常ならば 1 回の呼び出しで取得します。

DSS_FUNCTION では、コードのコンテキストに含まれる関数を逆アセンブルすることを指定します。 によって返されるときに混合モードのストリームが、関数を表すことを指定、 [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)メソッド。

によって返される DSS_MODULE とき、`IDebugDisassemblyStream2::GetScope`メソッドでは、混合モードのストリームがモジュールを表すことを指定します。

アドレス空間全体の DSS_ALL 指定逆アセンブリ

## <a name="remarks"></a>Remarks
引数として渡される、 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)メソッドによって返されると、 [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)メソッド。

これらの値は、演算と組み合わせることがあります`OR`します。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)
- [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)
