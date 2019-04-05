---
title: Idiasectioncontrib::get_code16bit |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_code16bit method
ms.assetid: 8cde8fc5-9546-4f82-b4a8-afd0d835039e
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1aceb4956b7ce2517087511676ebeff2b061b673
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973796"
---
# <a name="idiasectioncontribgetcode16bit"></a>IDiaSectionContrib::get_code16bit
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

セクションに 16 ビットのコードが含まれているかどうかを示すフラグを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_code16bit(  
   BOOL *pRetVal  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]返します`TRUE`セクションのコードが 16 ビット、それ以外の場合は、返す`FALSE`します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドでは、コードは 16 ビットをのみを示します。 コードがない 16 ビットの場合は、32 ビットまたは 64 ビットのコードなどの他に何も可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
