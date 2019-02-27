---
title: 'VsgDbg:: ~ VsgDbg (デストラクター) |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7a3b97fb-d344-4df7-b195-9347d1edfcf7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 64d2ce58a0a543a6bccfca4d96ff57915d45ce49
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686562"
---
# <a name="vsgdbgvsgdbg-destructor"></a>VsgDbg::~VsgDbg (デストラクター)
`VsgDbg` クラスのインスタンスを破棄します。 グラフィックス情報がアクティブに記録されている場合、グラフィック ログ ファイルは終了して閉じられ、グラフィックス情報がアクティブにキャプチャされているときに使用されたリソースが解放されます。

## <a name="syntax"></a>構文

```C++
~VsgDbg();
```

## <a name="see-also"></a>関連項目
- [VsgDbg::VsgDbg (コンストラクター)](vsgdbg-vsgdbg-constructor.md)