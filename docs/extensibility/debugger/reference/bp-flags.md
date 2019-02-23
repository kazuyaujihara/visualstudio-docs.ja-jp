---
title: BP_FLAGS |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_FLAGS
helpviewer_keywords:
- BP_FLAGS enumeration
ms.assetid: c45dfc74-5e7f-4f1e-a147-ab2a55dccbd0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fe346d708110cf16b85e84d61aeb25ee335c0e96
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56688434"
---
# <a name="bpflags"></a>BP_FLAGS
ブレークポイントを設定するときに、追加情報を指定するために使用するオプションのフラグを提供します。

## <a name="syntax"></a>構文

```cpp
enum enum_BP_FLAGS {
    BP_FLAG_NONE            = 0x0000,
    BP_FLAG_MAP_DOCPOSITION = 0x0001,
    BP_FLAG_DONT_STOP       = 0x0002
};
typedef DWORD BP_FLAGS;
```

```csharp
public enum enum_BP_FLAGS {
    BP_FLAG_NONE            = 0x0000,
    BP_FLAG_MAP_DOCPOSITION = 0x0001,
    BP_FLAG_DONT_STOP       = 0x0002
};
```

## <a name="members"></a>メンバー
BP_FLAG_NONE はブレークポイント フラグを指定します。

BP_FLAG_MAP_DOCPOSITION では、デバッグ エンジン (DE) がドキュメントの位置を使用してブレークポイントをマップする必要がありますを指定します。 これは、機能は、Active Server Pages (ASP) などのスクリプトを使用したソース ファイルに設定されたブレークポイントにのみ適用されます。

ブレークポイントは、デバッグ エンジンで処理する必要がありますが、最終的には、デバッグ エンジンがありますに停止する必要があります BP_FLAG_DONT_STOP を指定します (つまり、 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)イベント オブジェクトを送信しない必要があります)。 このフラグは、トレース ポイントで主に使用する設計されています。

## <a name="remarks"></a>Remarks
使用、`dwFlags`のメンバー、 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)と[BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)構造体。

これらの値は、演算と組み合わせることがあります`OR`します。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)
- [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
- [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)
