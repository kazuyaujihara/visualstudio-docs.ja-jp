---
title: IDebugSettingsCallback2::GetEEMetricDword | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::GetEEMetricDword
ms.assetid: c5f8f417-0ef0-4fd0-a779-b0a8ead4effe
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 475a2a22e148c1b2849d469889492f7eb271e7e1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56697651"
---
# <a name="idebugsettingscallback2geteemetricdword"></a>IDebugSettingsCallback2::GetEEMetricDword
式エバリュエーターの指定したメトリックに対応する値を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetEEMetricDword(
   REFGUID guidLang,
   REFGUID guidVendor,
   LPCWSTR pszMetric,
   DWORD*  pdwValue
);
```

```csharp
private int GetEEMetricDword(
   ref Guid guidLang,
   ref Guid guidVendor,
   string   pszMetric,
   out uint pdwValue
);
```

#### <a name="parameters"></a>パラメーター
 `guidLang`

 [in]プログラミング言語の一意の識別子。

 `guidVendor`

 [in]ベンダーの一意の識別子。

 `pszMetric`

 [in]メトリックの名前。

 `pdwValue`

 [out]メトリックの文字列に対応する値を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)