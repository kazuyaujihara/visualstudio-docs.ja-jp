---
title: Idiaimagedata::get_imagebase |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaImageData::get_imageBase method
ms.assetid: 4ba3d9e4-b205-4ee6-a41d-6996972f1f85
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: de8c333391530cd86c6fc66a8e6c36ce8cfecd5f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62829063"
---
# <a name="idiaimagedatagetimagebase"></a>IDiaImageData::get_imageBase
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

イメージのベースでのメモリ位置を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_imageBase (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]推奨されるイメージのベース値を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 イメージ ベースの競合によってイメージは、可能性がありますにリベースされます自動的には、未使用のメモリの場所が読み込まれるときにします。 このメソッドは、コンパイル時に、モジュールに格納された基本ヒント (推奨されるメモリの場所) を返します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)
