---
title: SccGetVersion 関数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccGetVersion
helpviewer_keywords:
- SccGetVersion function
ms.assetid: a6e786bf-744e-4272-9e21-0be44d23b1a1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7e2b3818aaa5097313d9150b365544267768507f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56708941"
---
# <a name="sccgetversion-function"></a>SccGetVersion 関数
この関数は、ソース管理プラグインでサポートされているソース管理プラグイン API のバージョン番号を取得します。

## <a name="syntax"></a>構文

```cpp
LONG SccGetVersion(void);
```

#### <a name="parameters"></a>パラメーター
 なし。

## <a name="return-value"></a>戻り値
 A`LONG`サポートされているソース管理プラグイン API のバージョン番号を含むデータ型。

|WORD|説明|
|----------|-----------------|
|HIWORD|メジャー バージョン|
|LOWORD マクロ|マイナー バージョン|

## <a name="remarks"></a>Remarks
 ソース管理プラグインは、ソース管理プラグイン API のバージョン 1.3 をサポートする場合など、この関数では、0x0103 に返します。

## <a name="see-also"></a>関連項目
- [ソース管理プラグインの API 関数](../extensibility/source-control-plug-in-api-functions.md)