---
title: IDebugSettingsCallback2::GetMetricGuid |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::GetMetricGuid
ms.assetid: 91092763-3362-4857-adf0-231bc1254206
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 49f30f6b5bb1231f6bcbd77097454ae7a73a7a2c
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458592"
---
# <a name="idebugsettingscallback2getmetricguid"></a>IDebugSettingsCallback2::GetMetricGuid
指定した名前のメトリックの一意の識別子を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetMetricGuid(
   LPCWSTR pszType,
   REFGUID guidSection,
   LPCWSTR pszMetric,
   GUID*   pguidValue
);
```

```csharp
private int GetMetricGuid(
   string   pszType,
   ref Guid guidSection,
   string   pszMetric,
   out Guid pguidValue
);
```

## <a name="parameters"></a>パラメーター
 `pszType`\

 [in]メトリックの種類です。

 `guidSection`\

 [in]セクションの一意の識別子。

 `pszMetric`\

 [in]メトリックの名前。

 `pguidValue`\

 [out]メトリックの一意の識別子を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)