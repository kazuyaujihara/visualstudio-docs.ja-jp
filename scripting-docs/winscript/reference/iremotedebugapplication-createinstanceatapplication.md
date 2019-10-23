---
title: 'IRemoteDebugApplication:: CreateInstanceAtApplication |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplication.CreateInstanceAtApplication
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplication::CreateInstanceAtApplication
ms.assetid: d669ec80-2182-400d-87cc-7c1753315e5c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 285e5df6960e3188ffe1ce17b1fc4f43626a3d74
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572312"
---
# <a name="iremotedebugapplicationcreateinstanceatapplication"></a>IRemoteDebugApplication::CreateInstanceAtApplication
アプリケーションに対してプロセス外のコードを使用して、アプリケーションプロセス内のオブジェクトを作成できるようにします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CreateInstanceAtApplication(  
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
  
## <a name="see-also"></a>関連項目  
 [IRemoteDebugApplication インターフェイス](../../winscript/reference/iremotedebugapplication-interface.md)