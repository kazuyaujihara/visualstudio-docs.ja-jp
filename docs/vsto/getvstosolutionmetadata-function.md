---
title: GetVstoSolutionMetadata 関数
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d7714e78e897e6c8b391a6c30e9a548671ce80c4
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635008"
---
# <a name="getvstosolutionmetadata-function"></a>GetVstoSolutionMetadata 関数
  この API は、オフィスのインフラストラクチャをサポートしているし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```csharp
HRESULT WINAPI GetVstoSolutionMetadata(
    LPCWSTR lpwszSolutionMetadataKey,
    ISolutionMetadata** ppSolutionInfo
);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*lpwszSolutionMetadataKey*|使用しないでください。|
|*ppSolutionInfo*|使用しないでください。|

## <a name="return-value"></a>戻り値
 返します、関数が成功したかどうかは**S_OK**します。 関数が失敗した場合、エラー コードを返します。
