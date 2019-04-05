---
title: Idiasourcefile::get_filename |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_fileName method
ms.assetid: a5cb8927-23c6-469e-8f78-f2787d85dba4
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 718b84720c3dbfc03552b6b64a95645e72951057
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58972409"
---
# <a name="idiasourcefilegetfilename"></a>IDiaSourceFile::get_fileName
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

ソース ファイル名を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_fileName (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]ソース ファイル名を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
