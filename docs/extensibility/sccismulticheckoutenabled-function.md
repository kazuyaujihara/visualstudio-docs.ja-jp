---
title: SccIsMultiCheckoutEnabled 関数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccIsMultiCheckoutEnabled
helpviewer_keywords:
- SccIsMultiCheckoutEnabled function
ms.assetid: 6721639d-e475-4766-81b5-ee40a280fc70
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dd8fb5439ac68200ba1a3bbf3af665595528173e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72721080"
---
# <a name="sccismulticheckoutenabled-function"></a>SccIsMultiCheckoutEnabled 関数
この関数は、ソース管理プラグインがファイルに対して複数のチェックアウトを許可しているかどうかを確認します。

## <a name="syntax"></a>構文

```cpp
SCCRTN SccIsMultiCheckoutEnabled(
   LPVOID pContext,
   LPBOOL pbMultiCheckout
);
```

#### <a name="parameters"></a>パラメーター
 pContext

からソース管理プラグインのコンテキスト構造。

 pbMultiCheckout

入出力このプロジェクトに対して複数のチェックアウトを有効にするかどうかを指定します (0 以外の場合は複数のチェックアウトがサポートされます)。

## <a name="return-value"></a>戻り値
 この関数のソース管理プラグインの実装では、次の値のいずれかが返されることが想定されています。

|[値]|説明|
|-----------|-----------------|
|SCC_OK|チェックに成功しました。|
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|不特定のエラーです。|

## <a name="remarks"></a>Remarks
 IDE は2つのチェックを行い、複数のユーザーが同時にファイルをチェックアウトできるかどうかを判断します。 まず、ソース管理システムが複数のチェックアウトをサポートしている必要があります。 ソース管理プラグインは、`SCC_CAP_MULTICHECKOUT` を指定することにより、初期化中にこの機能を指定できます。 その後、2番目のチェックとして、IDE はこの関数を呼び出して、現在のプロジェクトが複数のチェックアウトをサポートしているかどうかを判断します。 選択したプロジェクトで複数のチェックアウトがサポートされている場合、プラグインは成功コードを返し、`pbMultiCheckout` を0以外 (`TRUE`) または `FALSE` に設定します。

## <a name="see-also"></a>関連項目
- [ソース管理プラグインの API 関数](../extensibility/source-control-plug-in-api-functions.md)