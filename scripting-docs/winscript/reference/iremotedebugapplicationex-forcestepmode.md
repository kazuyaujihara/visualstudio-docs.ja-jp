---
title: IRemoteDebugApplicationEx:ForceStepMode |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationEx:ForceStepMode
apilocation:
- scrobj.dll
helpviewer_keywords:
- IRemoteDebugApplicationEx:ForceStepMode
ms.assetid: 83e69a3e-e4c9-4ddd-b01b-1820e4177a03
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 04a2c700d2cac4bcdc845ebf442de29863e87deb
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58159492"
---
# <a name="iremotedebugapplicationexforcestepmode"></a>IRemoteDebugApplicationEx:ForceStepMode

シングル ステップ モードにデバッガーを強制します。

## <a name="syntax"></a>構文

```cpp
HRESULT ForceStepMode(
   IRemoteDebugApplicationThread*  pStepThread
);
```

### <a name="parameters"></a>パラメーター

`pStepThread`

[in]ステップ イン プロセスのデバッグ モニターのスレッド。 Null の場合、PDM は、ステップ実行のスレッドをクリアします。

## <a name="return-value"></a>戻り値

このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。

|[値]|説明|
|-----------|-----------------|
|`S_OK`|メソッドが成功しました。|

## <a name="see-also"></a>関連項目

- [IRemoteDebugApplicationEx インターフェイス](iremotedebugapplicationex-interface.md)