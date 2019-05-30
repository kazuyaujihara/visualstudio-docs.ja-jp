---
title: IDebugFirewallConfigurationCallback2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugFirewallConfigurationCallback2 interface
ms.assetid: 0827361c-b97c-4851-9898-ab6d88c81811
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 09b4c04b996d180f1975ee1e9ad3a9a95cd1b76a
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66337457"
---
# <a name="idebugfirewallconfigurationcallback2"></a>IDebugFirewallConfigurationCallback2
要求に DCOM を使用するデバッグ エンジンを有効、[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]ファイアウォールをリモート デバッグするブロックはしないことを確認するための UI。

## <a name="syntax"></a>構文

```
IDebugFirewallConfigurationCallback2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 セッション デバッグ マネージャーのポート オブジェクトによって実装されます。

## <a name="methods"></a>メソッド
 次の表は、メソッドの`IDebugFirewallConfigurationCallback2`します。

|メソッド|説明|
|------------|-----------------|
|[EnsureDCOMUnblocked](../../../extensibility/debugger/reference/idebugfirewallconfigurationcallback2-ensuredcomunblocked.md)|ファイアウォール ブロックされていないことのリモート デバッグを要求します。|

## <a name="requirements"></a>必要条件
 ヘッダー:Msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll