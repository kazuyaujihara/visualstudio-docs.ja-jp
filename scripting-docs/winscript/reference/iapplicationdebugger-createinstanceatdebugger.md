---
title: 'IApplicationDebugger:: CreateInstanceAtDebugger |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IApplicationDebugger.CreateInstanceAtDebugger
apilocation:
- scrobj.dll
helpviewer_keywords:
- IApplicationDebugger::CreateInstanceAtDebugger
ms.assetid: 6763afac-c86a-4e88-9580-77108fb242fb
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c15dc5d9b36a718ed41813bac46bc4b9415eb853
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577889"
---
# <a name="iapplicationdebuggercreateinstanceatdebugger"></a>IApplicationDebugger::CreateInstanceAtDebugger
デバッガーに対してプロセス外のコードを使用して、デバッガープロセスでオブジェクトを作成できるようにします。  
  
> [!IMPORTANT]
> 信頼されていないコードが信頼されたデバッガースレッドで任意のオブジェクトを作成できるようにするため、このメソッドを実装することはできません。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CreateInstanceAtDebugger(  
   REFCLSID    rclsid,  
   IUnknown*   pUnkOuter,  
   DWORD       dwClsContext,  
   REFIID      riid,  
   IUnknown**  ppvObject  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `rclsid`  
 から作成するオブジェクトのクラス識別子 (CLSID)。  
  
 `pUnkOuter`  
 から@No__t_0 した場合、オブジェクトは集計の一部として作成されません。 それ以外の場合、`pUnkOuter` は、集約オブジェクトの `IUnknown` インターフェイス (制御 `IUnknown`) へのポインターです。  
  
 `dwClsContext`  
 から実行可能コードを実行するためのコンテキスト。 値は、列挙 `CLSCTX` から取得されます。  
  
 `riid`  
 からオブジェクトとの通信に使用されるインターフェイス識別子。  
  
 `ppvObject`  
 入出力@No__t_0 に要求されたインターフェイスポインターを受け取るポインター変数のアドレス。 正常に返された場合は、要求されたインターフェイスポインターが * `ppvObject` に含まれます。 エラーが発生すると、\* `ppvObject` に `NULL` が含まれます。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、`CoCreateInstance` にデリゲートします。  
  
 メソッドは現在実装されていません。  
  
## <a name="see-also"></a>関連項目  
 [IApplicationDebugger インターフェイス](../../winscript/reference/iapplicationdebugger-interface.md)