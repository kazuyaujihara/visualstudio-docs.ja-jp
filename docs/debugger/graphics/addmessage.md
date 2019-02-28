---
title: AddMessage |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 41a71a69c916bf2fff30b2dee8784d5d9997436b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56705571"
---
# <a name="addmessage"></a>AddMessage
グラフィックス診断の *HUD* (ヘッドアップ ディスプレイ) にカスタム メッセージを追加します。

## <a name="syntax"></a>構文

```C++
void AddMessage(
  wchar_t const * szMessage
);
```

#### <a name="parameters"></a>パラメーター
 `szMessage` HUD に追加するメッセージ。

## <a name="remarks"></a>解説
 グラフィックス診断の HUD は、グラフィック診断で実行されているアプリケーションの左上隅に表示されます。 これには、アプリケーションとグラフィックス情報キャプチャのランタイム情報、およびこの関数の呼び出しによって追加されたメッセージが表示されます。

 HUD にメッセージを追加するには、アクティブにグラフィックス情報をキャプチャする必要はありません。メッセージは、`VsgDbg` クラスのインスタンスを使用して追加できますが、[Init](init.md) メンバー関数は最初に呼び出されません。 メッセージは HUD に表示されるだけで、グラフィックのログ ファイルには記録されません。