---
title: IDebugReference2::SetValueAsString |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReference2::SetValueAsString
helpviewer_keywords:
- IDebugReference2::SetValueAsString
ms.assetid: 9a508ced-fd54-44f5-bb42-ec15c80384d7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b36b579f46739fd6ff554f2087be07ccd6bb69d5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68178164"
---
# <a name="idebugreference2setvalueasstring"></a>IDebugReference2::SetValueAsString
文字列からの参照の値を設定します。 将来使用するために予約されています。

## <a name="syntax"></a>構文

```cpp
HRESULT SetValueAsString ( 
   LPCOLESTR pszValue,
   DWORD     dwRadix,
   DWORD     dwTimeout
);
```

```csharp
int SetValueAsString ( 
   string pszValue,
   uint   dwRadix,
   uint   dwTimeout
);
```

#### <a name="parameters"></a>パラメーター
 `pszValue`

 [in]文字列としての値。

 `dwRadix`

 [in]任意の数値情報を書式設定で使用する基数。

 `dwTimeout`

 [in]このメソッドから戻る前に待機するミリ秒単位で最大時間。 使用`INFINITE`を無期限に待機します。

## <a name="return-value"></a>戻り値
 常に `E_NOTIMPL` を返します。

## <a name="see-also"></a>関連項目
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)