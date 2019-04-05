---
title: CaptureCurrentFrame |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2718e800e2a31eb66319259ed1e43f2ab8b084c5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58962808"
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

現在のフレームの残りの部分を、グラフィックス ログ ファイルにキャプチャします。  
  
## <a name="syntax"></a>構文  
  
```cpp  
void CaptureCurrentFrame();  
```  
  
## <a name="remarks"></a>Remarks  
 `BeginCapture` 関数によって開始されたキャプチャなど、別のキャプチャ操作が進行中の場合、そのキャプチャ操作は完了し、別個のフレームとしてグラフィックス ログに記録されます。 その直後、グラフィックス診断によって現在のフレームの残りの部分のキャプチャが開始され、それも個別のフレームとして記録されます。 present への呼び出しによって、現在のフレームの末尾がマークされます。  
  
 フレームをキャプチャするには、キャプチャしてグラフィックス情報を記録するアプリを準備する必要があります: 呼び出したする必要があります、 [Init](../debugger/init.md)のインスタンスを通じて、`VsgDbg`クラスを呼び出す前に`CaptureCurrentFrame`します。  
  
## <a name="see-also"></a>関連項目  
 [Init](../debugger/init.md)   
 [BeginCapture](../debugger/begincapture.md)
