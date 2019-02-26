---
title: IDebugProperty2::SetValueAsString |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::SetValueAsString
helpviewer_keywords:
- IDebugProperty2::SetValueAsString
ms.assetid: 9e6a5054-41b7-4223-b509-b93689d366a5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6acc3c0c0ec271793832783b2fb7eb9f2ff2309a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686485"
---
# <a name="idebugproperty2setvalueasstring"></a>IDebugProperty2::SetValueAsString
指定した文字列からプロパティの値を設定します。

## <a name="syntax"></a>構文

```cpp
HRESULT SetValueAsString ( 
   LPCOLESTR pszValue,
   UINT      nRadix,
   DWORD     dwTimeout
);
```

```csharp
int SetValueAsString ( 
   string pszValue,
   uint   nRadix,
   uint   dwTimeout
);
```

#### <a name="parameters"></a>パラメーター
 `pszValue`

 [in]設定する値を含む文字列。

 `nRadix`

 [in]任意の数値情報を解釈するときに使用する基数。 これは、自動的に基数を判断しようとする場合は 0 です。

 `dwTimeout`

 [in]このメソッドから戻る前に待機するミリ秒単位で最大の時間を指定します。 使用`INFINITE`を無期限に待機します。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`; エラー コードを返します。 次の表では、使用可能なその他の値を示します。

|[値]|説明|
|-----------|-----------------|
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|文字列をプロパティの値に変換できませんでしたまたはプロパティの値を設定できませんでした。|
|`E_SETVALUE_VALUE_IS_READONLY`|プロパティは読み取り専用です。|

## <a name="see-also"></a>関連項目
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)