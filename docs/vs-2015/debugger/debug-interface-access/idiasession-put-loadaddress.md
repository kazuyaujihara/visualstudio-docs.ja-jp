---
title: Idiasession::put_loadaddress |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::put_loadAddress method
ms.assetid: b157b245-1ea0-4b80-8962-d8b278dbc742
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1be0bfd6d5a635dcff632e25421922697b3f0de6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977088"
---
# <a name="idiasessionputloadaddress"></a>IDiaSession::put_loadAddress
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

このシンボル ストアのシンボルに対応する実行可能ファイルの読み込みアドレスを設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT put_loadAddress (   
   ULONGLONG NewVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `NewVal`  
 [in]実行可能ファイルのアドレスをロードします。  
  
## <a name="remarks"></a>Remarks  
 シンボルの仮想アドレス (VA) プロパティは、このメソッドの値を使用して計算されます。 このプロパティは 0 以外設定されていない限り、仮想アドレスは計算されません。  
  
> [!NOTE]
>  取得する場合は、このメソッドを呼び出す必要があります、 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)オブジェクトし、シンボルで任意の仮想プロパティを使用する必要がある場合、オブジェクトの使用を開始する前にします。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
