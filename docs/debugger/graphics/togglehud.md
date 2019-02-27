---
title: ToggleHUD |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7261e01d-3c72-46ce-9fb3-5f33b2ddb901
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cb05bb6a424b5639e0ee98e96c80315c51081ace
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56688317"
---
# <a name="togglehud"></a>ToggleHUD
グラフィックス診断の *HUD* (ヘッドアップ ディスプレイ) オーバーレイのオンとオフを切り替えます。

## <a name="syntax"></a>構文

```C++
void ToggleHUD();
```

## <a name="remarks"></a>解説
 グラフィックス診断の HUD は、グラフィック診断で実行されているアプリケーションの左上隅に表示されます。 実行時情報、アプリケーションとグラフィックス情報のキャプチャ、および呼び出しによって追加されたメッセージが表示されます、 [AddMessage](addmessage.md)メンバー関数。

 HUD を切り替えるには、アクティブにグラフィックス情報をキャプチャする必要はありません。これは、`VsgDbg` クラスのインスタンスを通じて切り替えられますが、[Init](init.md) メンバー関数は最初に呼び出される必要はありません。