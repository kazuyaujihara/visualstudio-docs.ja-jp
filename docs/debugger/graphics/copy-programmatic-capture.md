---
title: コピー (プログラムによるキャプチャ) |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3a888605cfae6b5430782defd198f83988c31870
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719081"
---
# <a name="copy-programmatic-capture"></a>コピー (プログラムによるキャプチャ)
アクティブなグラフィックス ログ (.vsglog) ファイルの内容を、新しいファイルにコピーします。

## <a name="syntax"></a>構文

```C++
void Copy(
  wchar_t const * szNewVSGLog
);
```

#### <a name="parameters"></a>パラメーター
 `szNewVSGLog` 新しいグラフィックス ログ ファイルのファイル名。

## <a name="remarks"></a>解説
 グラフィックス情報を新しいファイルにコピーするには、グラフィック情報を既にキャプチャしている必要があります。していない場合は、何も実行されません。