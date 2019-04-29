---
title: IRemoteDebugApplicationEx:RevokeBreak |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationEx:RevokeBreak
apilocation:
- scrobj.dll
helpviewer_keywords:
- IRemoteDebugApplicationEx:RevokeBreak
ms.assetid: 1f077860-0a39-4ec9-b676-ae0712819c7b
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0992eb5637434ccdf0dbf4fa6e436c87ae3fdd6c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62788405"
---
# <a name="iremotedebugapplicationexrevokebreak"></a>IRemoteDebugApplicationEx:RevokeBreak

Break コマンドを取り消します。

## <a name="syntax"></a>構文

```cpp
HRESULT RevokeBreak( );
```

### <a name="parameters"></a>パラメーター

なし。

## <a name="return-value"></a>戻り値

このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。

|[値]|説明|
|-----------|-----------------|
|`S_OK`|メソッドが成功しました。|

## <a name="see-also"></a>関連項目

- [IRemoteDebugApplicationEx インターフェイス](iremotedebugapplicationex-interface.md)