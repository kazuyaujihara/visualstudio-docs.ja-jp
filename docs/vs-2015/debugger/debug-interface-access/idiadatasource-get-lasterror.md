---
title: Idiadatasource::get_lasterror |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::get_lastError method
ms.assetid: cf08850b-8b75-4e8c-90bd-bd0214756f99
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3ad0570436dda6ac9ae52325c891b32a563cf6f7
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58976306"
---
# <a name="idiadatasourcegetlasterror"></a>IDiaDataSource::get_lastError
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

最後の読み込みエラーのファイル名を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_lastError (  
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 pRetVal  
 [out]最後の読み込みエラーに関連付けられている .pdb ファイル名を含む文字列を返します。  
  
## <a name="return-value"></a>戻り値  
 読み込み操作による最後のエラー コードを返します。 返します`E_INVALIDARG`場合、`pRetVal`パラメーターが`NULL`します。  
  
## <a name="example"></a>例  
  
```cpp#  
BSTR    fileName;  
HRESULT errorCode = pSource->get_lastError( &fileName );  
```  
  
## <a name="see-also"></a>関連項目  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)
