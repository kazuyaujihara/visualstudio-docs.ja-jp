---
title: IDiaStackWalkHelper::frameForVA |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::frameForVA method
ms.assetid: f35fc61b-f8dd-473a-b583-82c304059422
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c4a36c31058912d1acc3d92e907954e48255c23a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68150130"
---
# <a name="idiastackwalkhelperframeforva"></a>IDiaStackWalkHelper::frameForVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

指定された仮想アドレスを含むスタック フレームを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT frameForVA(   
   ULONGLONG        va,  
   IDiaFrameData**  ppFrame  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `va`  
 [in]フレーム データの仮想アドレス。  
  
 `ppFrame`  
 [out][IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)指定のアドレスにあるスタック フレームを表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
