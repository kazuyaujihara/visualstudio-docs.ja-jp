---
title: コピー (プログラムによるキャプチャ) |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: fa79ffc2081ba92b905838658fe6aa758a675192
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58972458"
---
# <a name="copy-programmatic-capture"></a>コピー (プログラムによるキャプチャ)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

アクティブなグラフィックス ログ (.vsglog) ファイルの内容を、新しいファイルにコピーします。  
  
## <a name="syntax"></a>構文  
  
```cpp  
void Copy(  
  wchar_t const * szNewVSGLog  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `szNewVSGLog`  
 新しいグラフィックス ログ ファイルのファイル名。  
  
## <a name="remarks"></a>Remarks  
 グラフィックス情報を新しいファイルにコピーするには、グラフィック情報を既にキャプチャしている必要があります。していない場合は、何も実行されません。
