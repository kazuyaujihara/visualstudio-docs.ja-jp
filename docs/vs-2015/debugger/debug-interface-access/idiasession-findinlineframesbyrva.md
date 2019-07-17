---
title: IDiaSession::findInlineFramesByRVA |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
ms.assetid: ddb3ff0e-cb3d-4fa0-af56-f064b218b264
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1cb783936579eb3cd3c4903653ef6ad04e1bc381
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68151718"
---
# <a name="idiasessionfindinlineframesbyrva"></a>IDiaSession::findInlineFramesByRVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

により、クライアントは、すべての指定された相対仮想アドレス (RVA) でのインライン フレームを反復処理する列挙体を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT findInlineFramesByRVA (   
   IDiaSymbol*       parent,   DWORD             rva,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `parent`  
 [in]`IDiaSymbol`親を表すオブジェクト。  
  
 `rva`  
 [in]として、RVA アドレスを指定します。  
  
 `ppResult`  
 [out]保持する`IDiaEnumSymbols`取得されるフレームの一覧を含むオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
