---
title: IDebugProcessEx2::AddImplicitProgramNodes |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcessEx2::AddImplicitProgramNodes
helpviewer_keywords:
- IDebugProcessEx2::AddImplicitProgramNodes method
ms.assetid: 8b491b00-f9e7-45b3-9115-fe58c3464289
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6203b12defbe70d3807508953d85f39ff725a746
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56693520"
---
# <a name="idebugprocessex2addimplicitprogramnodes"></a>IDebugProcessEx2::AddImplicitProgramNodes
このメソッドは、指定された各デバッグ エンジン (DE) のプログラムのノードを追加します。

## <a name="syntax"></a>構文

```cpp
HRESULT AddImplicitProgramNodes(
   REFGUID guidLaunchingEngine,
   GUID*   rgguidSpecificEngines,
   DWORD   celtSpecificEngines
);
```

```csharp
int AddImplicitProgramNodes(
   ref Guid guidLaunchingEngine,
   Guid[]   rgguidSpecificEngines,
   uint     celtSpecificEngines
);
```

#### <a name="parameters"></a>パラメーター
 `guidLaunchingEngine`

 [in]`GUID`プログラムを起動するために使用するのには (および独自のプログラムのノードを追加すると見なされます) を DE の。

 `rgguidSpecificEngines`

 [in]配列の`GUID`の DEs ノードを追加するプログラムを選択します。

 `celtSpecificEngines`

 [in]数`GUID`内、`rgguidSpecificEngines`配列。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
- [プログラム ノード](../../../extensibility/debugger/program-nodes.md)各 DE の記載に追加`rgguidSpecificEngines`-起動エンジンを除外 (で指定されている`guidLaunchingEngine`)、プログラムを起動するときに、独自のプログラム ノードを追加すると見なされます。

## <a name="see-also"></a>関連項目
- [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)
- [プログラム ノード](../../../extensibility/debugger/program-nodes.md)