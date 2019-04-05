---
title: Idiasectioncontrib::get_comdat |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_comdat method
ms.assetid: 8bd9be8d-59ee-4698-b055-daba354b8dcc
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ddf479a2da74803916b7afc1945eb610d6b0e668
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58974218"
---
# <a name="idiasectioncontribgetcomdat"></a>IDiaSectionContrib::get_comdat
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

セクションは COMDAT レコードであるかどうかを示すフラグを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_comdat (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]返します`TRUE`セクションが COMDAT レコード以外の場合を返しますそれ以外の場合、`FALSE`します。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`場合、このプロパティはサポートされていません。 それ以外の場合はエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 COMDAT レコードとは、パッケージ化された関数をリンカーに表示する一般的なオブジェクト ファイル形式 (COFF) レコードです。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
