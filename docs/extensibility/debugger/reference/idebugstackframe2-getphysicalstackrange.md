---
title: IDebugStackFrame2::GetPhysicalStackRange |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetPhysicalStackRange
helpviewer_keywords:
- IDebugStackFrame2::GetPhysicalStackRange
ms.assetid: 2f6992e2-ac1c-433f-83b7-a7f83a4ce63d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ac507c2eac00d025a36bed3e4c3461a6b3fab2f0
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212861"
---
# <a name="idebugstackframe2getphysicalstackrange"></a>IDebugStackFrame2::GetPhysicalStackRange
スタック フレームに関連付けられている物理アドレスの範囲のマシンに依存する形式を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetPhysicalStackRange ( 
   UINT64* paddrMin,
   UINT64* paddrMax
);
```

```csharp
int GetPhysicalStackRange ( 
   out ulong paddrMin,
   out ulong paddrMax
);
```

## <a name="parameters"></a>パラメーター
`paddrMin`\
[out]このスタック フレームに関連付けられている最下位の物理アドレスを返します。

`paddrMax`\
[out]このスタック フレームに関連付けられている最上位の物理アドレスを返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 このメソッドによって返される情報は、スタック フレームの並べ替えにセッション デバッグ マネージャー (SDM) によって使用されます。

 呼び出し履歴が、ダウンされている拡張する、新しいスタック フレームがますます下位メモリ アドレスに追加されると見なされます。 実行時のアーキテクチャでは、この前提に一致する物理スタック範囲を提供する必要があります。

## <a name="see-also"></a>関連項目
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)