---
title: IDebugPortSupplier3 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugPortSupplier3
helpviewer_keywords:
- IDebugPortSupplier3 interface
ms.assetid: e458cd02-2370-4435-8953-17d7a60ce152
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e4ece720cf6880bba528dee99cdbdeb25c10087a
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65674127"
---
# <a name="idebugportsupplier3"></a>IDebugPortSupplier3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このインターフェイスは、ポート サプライヤーが (ディスクに書き込む) ことによって、デバッガーの呼び出しの間でポートを保持して、それらの保存されたポートの一覧を取得するかどうかを確認する呼び出し元を使用します。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugPortSupplier3 : IDebugPortSupplier2  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 カスタム ポート サプライヤーは、永続化やディスクへのポート情報の保存をサポートするには、このインターフェイスを実装します。 同じオブジェクトでこのインターフェイスを実装する必要があります、 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)インターフェイス。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 呼び出す[QueryInterface](https://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3)上、`IDebugPortSupplier2`をこのインターフェイスを取得するインターフェイス。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序メソッド  
 継承されたメソッドだけでなく、 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)インターフェイスでは、このインターフェイスは、次をサポートします。  
  
|メソッド|説明|  
|------------|-----------------|  
|[CanPersistPorts](../../../extensibility/debugger/reference/idebugportsupplier3-canpersistports.md)|ポート サプライヤーが、(ディスクに書き込む) ことによってポートをデバッガーの呼び出しの間で永続化できるかどうかを返します。|  
|[EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md)|このポートのサプライヤーによってディスクに書き込まれたすべてのポートを列挙するために使用できるオブジェクトを返します。|  
  
## <a name="remarks"></a>Remarks  
 ポート サプライヤーは、呼び出し間でポートを保持することができます、このインターフェイスを実装にする必要があります。 ポート サプライヤーのインスタンス化し、ポート サプライヤーが破棄されるときにディスクに書き込まれるときに、ポートを読み込む必要があります。  
  
 通常、デバッグ エンジンは、ポート サプライヤーと対話しないし、このインターフェイスの使用はありません。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
