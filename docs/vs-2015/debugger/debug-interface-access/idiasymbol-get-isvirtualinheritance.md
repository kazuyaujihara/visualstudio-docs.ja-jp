---
title: IDiaSymbol::get_isVirtualInheritance |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
ms.assetid: 72906b92-dd4a-42e3-9b24-b77628fa48c1
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 60126527e4c581979d5686696c7f2cbf6ae720eb
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "68200694"
---
# <a name="idiasymbolgetisvirtualinheritance"></a>IDiaSymbol::get_isVirtualInheritance
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

指定するかどうか、`this`仮想継承を持つデータ メンバーを指すポインター。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT get_isVirtualInheritance(   
   BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]ポインターを`BOOL`を指定するかどうか、`this`仮想継承を持つデータ メンバーを指すポインター。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
