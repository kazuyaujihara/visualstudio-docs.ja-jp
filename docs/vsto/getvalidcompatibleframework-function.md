---
title: GetValidCompatibleFramework 関数
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
ms.openlocfilehash: b975a4b4b2c1b4ae3f6ef0f1d6d23769bb4c77c7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62788697"
---
# <a name="getvalidcompatibleframework-function"></a>GetValidCompatibleFramework 関数
  この API は、オフィスのインフラストラクチャをサポートしているし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```csharp
HRESULT WINAPI GetValidCompatibleFramework(
    LPCWSTR lpwszCompatibleFrameworksXML,
    BSTR* pbstrValidFrameworkTag
);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*lpwszCompatibleFrameworksXML*|使用しないでください。|
|*pbstrValidFrameworkTag*|使用しないでください。|

## <a name="return-value"></a>戻り値
 返します、関数が成功したかどうかは**S_OK**します。 関数が失敗した場合、エラー コードを返します。
