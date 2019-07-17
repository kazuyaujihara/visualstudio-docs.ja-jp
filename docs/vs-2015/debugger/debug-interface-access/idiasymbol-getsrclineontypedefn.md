---
title: IDiaSymbol::getSrcLineOnTypeDefn |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
ms.assetid: ad554d18-9988-4b64-ad71-e7594c266e94
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a3a70cec3ab9e03dd97a1df5f0ccf8713a79cc28
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "68180481"
---
# <a name="idiasymbolgetsrclineontypedefn"></a>IDiaSymbol::getSrcLineOnTypeDefn
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

指定されたユーザー定義型が定義されているかを示すソース ファイルと行番号を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT getSrcLineOnTypeDefn(  
   IDiaLineNumber **ppResult);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppResult`  
 [out]A`IDiaLineNumber`ソース ファイルと行番号を格納しているオブジェクトをユーザー定義します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
