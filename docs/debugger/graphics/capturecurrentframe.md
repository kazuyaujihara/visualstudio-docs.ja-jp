---
title: CaptureCurrentFrame |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ec67013b41a5ec8876866044355534c42bfe2ee0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62848712"
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
現在のフレームの残りの部分を、グラフィックス ログ ファイルにキャプチャします。

## <a name="syntax"></a>構文

```C++
void CaptureCurrentFrame();
```

## <a name="remarks"></a>Remarks
 `BeginCapture` 関数によって開始されたキャプチャなど、別のキャプチャ操作が進行中の場合、そのキャプチャ操作は完了し、別個のフレームとしてグラフィックス ログに記録されます。 その直後、グラフィックス診断によって現在のフレームの残りの部分のキャプチャが開始され、それも個別のフレームとして記録されます。 present への呼び出しによって、現在のフレームの末尾がマークされます。

 フレームをキャプチャするには、キャプチャしてグラフィックス情報を記録するアプリを準備する必要があります: 呼び出したする必要があります、 [Init](init.md)のインスタンスを通じて、`VsgDbg`クラスを呼び出す前に`CaptureCurrentFrame`します。

## <a name="see-also"></a>関連項目
- [Init](init.md)
- [BeginCapture](begincapture.md)
