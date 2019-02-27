---
title: EndCapture |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 06084c3b-e065-49b6-968e-d578762fb871
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0ae024f0d91c980fa8e787b21c93d32a6431203e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56695532"
---
# <a name="endcapture"></a>EndCapture
`BeginCapture` で開始されたキャプチャ区間を終了します。

## <a name="syntax"></a>構文

```C++
void EndCapture();
```

## <a name="remarks"></a>解説
 特定種類の描画呼び出しに関するグラフィック情報だけをキャプチャするときなど、キャプチャ区間は通常 1 つのフレームのサブセットに及びます。 キャプチャ区間が present への呼び出しに及ぶ場合は、2 つのフレームのグラフィックス情報がキャプチャされます。 最初のフレームは、`BeginCapture` への呼び出しと present への呼び出しの間の区間に及びます。2 つ目のフレームは、present への呼び出しの後の最初の Direct3D イベントと `EndCapture` への呼び出しの間の区間に及びます。

 間隔をキャプチャするには、キャプチャしてグラフィックス情報を記録するアプリを準備する必要があります: 呼び出したする必要があります、 [Init](init.md)のインスタンスを通じて、`VsgDbg`クラスを呼び出す前に`BeginCapture`または`EndCapture`します。

## <a name="see-also"></a>参照
- [BeginCapture](begincapture.md)
- [CaptureCurrentFrame](capturecurrentframe.md)