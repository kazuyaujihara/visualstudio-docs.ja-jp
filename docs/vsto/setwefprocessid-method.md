---
title: SetWefProcessId メソッド
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
ms.openlocfilehash: 1352ccc9318061be4a2f9ad2da7d63715acd6721
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56603081"
---
# <a name="setwefprocessid-method"></a>SetWefProcessId メソッド
  Web 拡張機能フレームワーク (WEF) コンテンツを実行しているプロセス id を提供します。

## <a name="syntax"></a>構文

```csharp
HRESULT SetWefProcessId(
    [in] DWORD dwProcessId
);
```

#### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*dwProcessId*|WEF コンテンツを実行するために使用するプロセスの識別子です。|

## <a name="return-value"></a>戻り値
 メソッドが正常に完了したかどうかを示す HRESULT 値。

## <a name="remarks"></a>Remarks
 WEF content のプロセスの作成後が WEF コンテンツを実行する前に、このメソッドを呼び出す必要があります。

 開発環境を WEF content のプロセスにデバッガーをアタッチする場合は、環境は、このメソッドの実装でこの操作を実行する必要があります。
