---
title: IDebugCodeContext3 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugCodeContext3 interface
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 911869a1d727e466cbf2d43557946efaba1f7dd4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62922831"
---
# <a name="idebugcodecontext3"></a>IDebugCodeContext3
拡張、 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)モジュールとプロセスのインターフェイスの取得を有効にするインターフェイス。

## <a name="syntax"></a>構文

```
IDebugCodeContext3 : IDebugCodeContext2
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 デバッグ エンジンによって実装されで使用される、[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]パッケージのデバッグ。

## <a name="methods"></a>メソッド
 メソッドだけでなく、`IDebugCodeContext2`インターフェイスでは、このインターフェイスは、次のメソッドを実装します。

|メソッド|説明|
|------------|-----------------|
|[GetModule](../../../extensibility/debugger/reference/idebugcodecontext3-getmodule.md)|デバッグ モジュールのインターフェイスへの参照を取得します。|
|[GetProcess](../../../extensibility/debugger/reference/idebugcodecontext3-getprocess.md)|デバッグ プロセスのインターフェイスへの参照を取得します。|

## <a name="remarks"></a>Remarks
 これは、一般に、実装する必要はありませんが、省略可能なインターフェイスです。

## <a name="requirements"></a>必要条件
 ヘッダー:Msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll