---
title: Idiasession::getsymbolsbyaddr |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::getSymbolsByAddr method
ms.assetid: eafcc757-b488-487d-a063-ad3703ff42e8
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d2851c61945bc72544beec1acd5d6800663acdf1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68150232"
---
# <a name="idiasessiongetsymbolsbyaddr"></a>IDiaSession::getSymbolsByAddr
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

そのアドレスの順序でシンボルを検索する列挙子を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT getSymbolsByAddr(   
   IDiaEnumSymbolsByAddr** ppEnumbyAddr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppEnumbyAddr`  
 [out]返します、 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)オブジェクト。 このインターフェイスを使用して、メモリの場所でシンボル ストア内のシンボルを検索します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)
