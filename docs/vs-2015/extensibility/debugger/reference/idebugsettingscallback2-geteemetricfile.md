---
title: IDebugSettingsCallback2::GetEEMetricFile |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::GetEEMetricFile
ms.assetid: 3a0bf9e5-bbd2-4d15-840d-8244732787fc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 30b7822bcabbe2f283c25a3e22f1e650269e7e62
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68155201"
---
# <a name="idebugsettingscallback2geteemetricfile"></a>IDebugSettingsCallback2::GetEEMetricFile
式エバリュエーター メトリック ファイルが指定された名前またはメトリックを取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetEEMetricFile(
   REFGUID guidLang,
   REFGUID guidVendor,
   LPCWSTR pszMetric,
   BSTR*   pbstrValue
);
```

```csharp
private int GetEEMetricFile(
   ref Guid   guidLang,
   ref Guid   guidVendor,
   string     pszMetric,
   out string pbstrValue
);
```

#### <a name="parameters"></a>パラメーター
 `guidLang`

 [in]プログラミング言語の一意の識別子。

 `guidVendor`

 [in]ベンダーの一意の識別子。

 `pszMetric`

 [in]メトリックの名前。

 `pbstrValue`

 [out]メトリックのファイルの内容を文字列として返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)