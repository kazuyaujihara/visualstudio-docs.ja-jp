---
title: Idiainjectedsource::get_source |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_source method
ms.assetid: 3c0b5386-321f-4f8f-85cc-e2ee7b4cc3d2
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 856d0111e65b51b798dfe44a324c58c4db5457fd
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58964037"
---
# <a name="idiainjectedsourcegetsource"></a>IDiaInjectedSource::get_source
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

ソース コードのバイト数を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_source (   
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cbData`  
 [in]データ バッファーのサイズを表すバイトの数。  
  
 `pcbData`  
 [out]返されたバイト数を表すバイトの数を返します。 場合`data`は`NULL`、し`pcbData`はデータのバイトの合計数を使用できます。  
  
 `data[]`  
 [out]ソース バイトで格納されるバッファー。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`場合、このプロパティはサポートされていません。 それ以外の場合はエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)
