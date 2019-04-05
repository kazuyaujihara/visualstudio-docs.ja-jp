---
title: Idiaframedata::get_virtualaddress |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_virtualAddress method
ms.assetid: de137bee-132f-4aae-a067-9578b7a3e6d4
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2da9743b009c2867e269aa1f0596295d73581b97
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58963737"
---
# <a name="idiaframedatagetvirtualaddress"></a>IDiaFrameData::get_virtualAddress
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

フレームのコードの仮想アドレス (VA) を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_virtualAddress (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]フレームのコードの仮想アドレスを返します。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`場合、このプロパティはサポートされていません。 それ以外の場合はエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
