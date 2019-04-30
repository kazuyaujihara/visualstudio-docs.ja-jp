---
title: GetAutoInsertExtensions メソッド
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
ms.openlocfilehash: fb767ec7301a1d4e0f29003971b017339228fc9f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62972279"
---
# <a name="getautoinsertextensions-method"></a>GetAutoInsertExtensions メソッド
  デバッグ中に自動的に挿入される Office 用アプリに関する情報を取得します。

 このメソッドは将来使用するために予約されています。

## <a name="syntax"></a>構文

```csharp
HRESULT GetAutoInsertExtensions(
    [out, retval] SAFEARRAY(BSTR)* psaExtensionNames
);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*psaExtensionNames*|Office 用アプリの拡張機能名。|

## <a name="return-value"></a>戻り値
 メソッドが正常に完了したかどうかを示す HRESULT 値。

## <a name="remarks"></a>Remarks
 挿入する Office の各アプリは下の値に対応する Office アプリケーションの拡張機能名として返されます**HKEY_CURRENT_USER\Software\Microsoft\Office\WEF\Developer**します。 ホストは、レジストリでこれらの値を検索し、拡張機能を自動的に挿入する必要があります。
