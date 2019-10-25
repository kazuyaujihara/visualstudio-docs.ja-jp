---
title: 'IDiaSession:: findInjectedSource |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findInjectedSource method
ms.assetid: 907531b6-1ef8-4153-986d-b72611a1632d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5e2145c90c25c448880e51b9b394c7085e0d49b7
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72742252"
---
# <a name="idiasessionfindinjectedsource"></a>IDiaSession::findInjectedSource
属性プロバイダーまたはコンパイルプロセスの他のコンポーネントによってシンボルストアに配置されたソースの一覧を取得します。

## <a name="syntax"></a>構文

```C++
HRESULT findInjectedSource ( 
   LPCOLESTR                 srcFile,
   IDiaEnumInjectedSources** ppResult
);
```

#### <a name="parameters"></a>パラメーター
 srcFile

から検索するソースファイルの名前。

 ppResult

入出力挿入されたすべてのソースの一覧を含む[IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)オブジェクトを返します。

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="see-also"></a>関連項目
- [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)