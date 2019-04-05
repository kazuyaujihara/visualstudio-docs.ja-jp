---
title: Idiasymbol::get_iscvtcil |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isCVTCIL method
ms.assetid: 711b81fd-9549-44dc-9761-5eb862ed64c0
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: da3744b51966fea9fea56f2f6d5c845d9328ccbe
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58963090"
---
# <a name="idiasymbolgetiscvtcil"></a>IDiaSymbol::get_isCVTCIL
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

共通中間言語 (CIL) モジュールからネイティブのモジュールにモジュールが変換されたかどうかを示すフラグを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_isCVTCIL(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pFlag`  
 [out]返します`TRUE`モジュールは、ネイティブ コードに CIL から変換された場合を返しますそれ以外の場合、`FALSE`します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
>  戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。  
  
## <a name="remarks"></a>Remarks  
 このプロパティは、`SymTagCompilandDetails`記号の型 (を参照してください[CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)します。  
  
## <a name="requirements"></a>必要条件  
  
|必要条件|説明|  
|-----------------|-----------------|  
|ヘッダー:|Dia2.h|  
|バージョン:|DIA SDK バージョン 8.0|  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)
