---
title: 'IDiaLoadCallback:: RestrictRegistryAccess |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback::RestrictRegistryAccess method
ms.assetid: de4760c3-a746-4bab-8065-1388fed31b67
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a2240ef2d20b46e50e36942553d76b83fce6232b
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743052"
---
# <a name="idialoadcallbackrestrictregistryaccess"></a>IDiaLoadCallback::RestrictRegistryAccess
シンボル検索パスを検索するためにレジストリクエリを使用できるかどうかを決定します。

## <a name="syntax"></a>構文

```C++
HRESULT RestrictRegistryAccess();
```

## <a name="return-value"></a>戻り値
 成功した場合は `S_OK` を返します。それ以外の場合は、エラーコードを返します。

## <a name="remarks"></a>Remarks
 @No__t_0 以外のリターンコードは、シンボル検索パスのレジストリに対してクエリを実行できません。

## <a name="see-also"></a>関連項目
- [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)