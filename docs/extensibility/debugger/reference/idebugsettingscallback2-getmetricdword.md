---
title: IDebugSettingsCallback2::GetMetricDword |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::GetMetricDword
ms.assetid: 831a5a1a-c4af-4520-9fdf-3a731aeff85c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f52205cd530e638146abe423890d6477fe62b45d
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457332"
---
# <a name="idebugsettingscallback2getmetricdword"></a>IDebugSettingsCallback2::GetMetricDword
指定した名前のメトリックの値を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetMetricDword(
   LPCWSTR pszType,
   REFGUID guidSection,
   LPCWSTR pszMetric,
   DWORD*  pdwValue
);
```

```csharp
private int GetMetricDword(
   string   pszType,
   ref Guid guidSection,
   string   pszMetric,
   out uint pdwValue
);
```

## <a name="parameters"></a>パラメーター
 `pszType`\

 [in]メトリックの種類です。

 `guidSection`\

 [in]セクションの一意の識別子。

 `pszMetric`\

 [in]メトリックの名前。

 `pdwValue`\

 [out]メトリックの値を返します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)