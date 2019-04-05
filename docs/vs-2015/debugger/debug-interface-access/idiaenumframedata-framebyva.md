---
title: Idiaenumframedata::framebyva |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::frameByVA method
ms.assetid: 0b1e441b-710a-46d8-8060-bed39071c834
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d0560965858bd6d9ee823a6056332bdd9a7b654a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58975464"
---
# <a name="idiaenumframedataframebyva"></a>IDiaEnumFrameData::frameByVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

仮想アドレス (VA) でフレームを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT frameByVA(   
   ULONGLONG       virtualAddress,  
   IDiaFrameData** frame  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 virtualAddress  
 [in]目的のフレームの VA します。  
  
 フレーム  
 [out]返します、 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)を指定したアドレスを含むフレームを表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`フレーム データに指定されたアドレスが一致しない場合。 それ以外の場合はエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
