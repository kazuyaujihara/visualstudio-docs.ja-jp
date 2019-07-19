---
title: IDiaSourceFile::get_uniqueId | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_uniqueId method
ms.assetid: e0b8dbc0-6061-4f31-bead-2cd72be44e41
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e5237d8a524bd77f67c86a650bb4c8f075e407fb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68190630"
---
# <a name="idiasourcefilegetuniqueid"></a>IDiaSourceFile::get_uniqueId
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

このイメージに対して一意である単純な整数キー値を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_uniqueId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]このイメージに対して一意である単純な整数キー値を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 文字列には、行番号の処理が高速化できるのではなくキーの比較。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
