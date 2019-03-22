---
title: IRemoteDebugApplicationEx:GetHostPid |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationEx:GetHostPid
apilocation:
- scrobj.dll
helpviewer_keywords:
- IRemoteDebugApplicationEx:GetHostPid
ms.assetid: 4cf9f46c-29cf-4201-87f0-5b1ddbed2f2b
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d660cce006e7f84f1b1c01f1ec0a406b5c4b9df3
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58152160"
---
# <a name="iremotedebugapplicationexgethostpid"></a>IRemoteDebugApplicationEx:GetHostPid

ホスト アプリケーションのプロセス ID を返します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetHostPid(
   DWORD*  dwHostPid
);
```

### <a name="parameters"></a>パラメーター

`dwHostPid`

[out]ホスト プロセス識別子。

## <a name="return-value"></a>戻り値

このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。

|[値]|説明|
|-----------|-----------------|
|`S_OK`|メソッドが成功しました。|

## <a name="remarks"></a>Remarks

IDE で使用されます。

## <a name="see-also"></a>関連項目

- [IRemoteDebugApplicationEx インターフェイス](iremotedebugapplicationex-interface.md)