---
title: IDebugBreakpointChecksumRequest2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugBreakpointChecksumRequest2 interface
ms.assetid: 9cfdbca5-052c-48e9-8411-e2e9e4065d00
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dfad0d8469a3cd01b5697cd9ba74f7a84ee84b83
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56706276"
---
# <a name="idebugbreakpointchecksumrequest2"></a>IDebugBreakpointChecksumRequest2
ブレークポイント要求のチェックサムをドキュメントを表します。

## <a name="syntax"></a>構文

```
IDebugBreakpointChecksumRequest2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 によって実装される、[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]デバッグ パッケージ化とデバッグ エンジンで使用します。

## <a name="methods"></a>メソッド
 次の表は、メソッドの`IDebugBreakpointChecksumRequest2`します。

|メソッド|説明|
|------------|-----------------|
|[GetChecksum](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2-getchecksum.md)|使用するチェックサム アルゴリズムの一意の識別子を指定されたブレークポイント要求のドキュメントのチェックサムを取得します。|
|[IsChecksumEnabled](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2-ischecksumenabled.md)|このドキュメントのチェックサムが有効になっているかどうかを決定します。|

## <a name="requirements"></a>必要条件
 ヘッダー:Msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll