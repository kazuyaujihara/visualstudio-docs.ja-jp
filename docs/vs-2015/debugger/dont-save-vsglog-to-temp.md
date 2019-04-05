---
title: DONT_SAVE_VSGLOG_TO_TEMP |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: f27ab0e6-9575-4ca0-9901-37d3e5c3a2f5
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 449c6c1ecdb0644b9b52b6ec12ce867dc34d66c4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977682"
---
# <a name="dontsavevsglogtotemp"></a>DONT_SAVE_VSGLOG_TO_TEMP
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

その存在によって、グラフィックス ログ ファイルがユーザーの一時ファイル ディレクトリに保存されるかどうかを定義します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
#define DONT_SAVE_VSGLOG_TO_TEMP  
```  
  
## <a name="value"></a>[値]  
 その有無によって、グラフィックス ログ ファイルがユーザーの一時ファイル ディレクトリに保存されるかどうかが決まるプリプロセッサ シンボル。 このシンボルが定義されている場合、`VSG_DEFAULT_RUN_FILENAME` で定義されるファイル名は、キャプチャされるアプリケーションの現在のディレクトリに対する相対パスになるか、または絶対パスです。それ以外の場合、`VSG_DEFAULT_RUN_FILENAME` で定義されるファイル名は、ユーザーの一時ファイル ディレクトリに対する相対パスになり、絶対パスにすることはできません。  
  
## <a name="remarks"></a>Remarks  
 ユーザーの特権によっては、グラフィック ログ ファイルを任意の場所に保存できないことがあります。 選択した場所にユーザーが書き込むことができるかどうかがわからない場合は、ユーザーの一時ファイル ディレクトリ、または別の既知の場所にグラフィックス ログを保存することをお勧めします。  
  
 グラフィックス ログ ファイルが一時ファイル ディレクトリに保存されていることを防ぐために定義する必要があります`DONT_SAVE_VSGLOG_TO_TEMP`インクルードする前に`vsgcapture.h`します。  
  
## <a name="example"></a>例  
 次の例に、グラフィックス ログ ファイルをホスト コンピューターの絶対パスに保存する方法を示します。  
  
```  
// Define DONT_SAVE_VSGLOG_TO_TEMP and VSG_DEFAULT_RUN_FILENAME before including vsgcapture.h  
#define DONT_SAVE_VSGLOG_TO_TEMP  
#define VSG_DEFAULT_RUN_FILENAME L"C:\\Graphics Diagnostics Captures\\default.vsglog"  
  
#include <vsgcapture.h>  
  
```  
  
## <a name="see-also"></a>関連項目  
 [VSG_DEFAULT_RUN_FILENAME](../debugger/vsg-default-run-filename.md)
