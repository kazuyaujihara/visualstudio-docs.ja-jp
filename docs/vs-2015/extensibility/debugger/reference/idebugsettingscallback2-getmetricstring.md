---
title: IDebugSettingsCallback2::GetMetricString |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::GetMetricString
- GetMetricString
ms.assetid: ecc875a2-8ac6-444c-a839-5191a780fd6b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f20348cdced520b4153f02d2320fcabcd266273d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68164834"
---
# <a name="idebugsettingscallback2getmetricstring"></a>IDebugSettingsCallback2::GetMetricString
指定した名前のメトリックの値の文字列を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetMetricString(
    LPCWSTR pszType,
    REFGUID guidSection,
    LPCWSTR pszMetric,
    BSTR*   pbstrValue
);
```

```csharp
private int GetMetricString(
    string     pszType,
    ref Guid   guidSection,
    string     pszMetric,
    out string pbstrValue
);
```

#### <a name="parameters"></a>パラメーター
 `pszType`

 [in]メトリックの種類です。

 `guidSection`

 [in]セクションの一意の識別子。

 `pszMetric`

 [in]メトリックの名前。

 `pbstrValue`

 [out]メトリックの値の文字列を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)