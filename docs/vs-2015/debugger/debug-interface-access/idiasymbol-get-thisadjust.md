---
title: Idiasymbol::get_thisadjust |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_thisAdjust method
ms.assetid: 56b9a147-e8c0-4d4b-a42a-398214dd5f86
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e4750c3801a96149866f88e3150fd495399b85d1
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58963316"
---
# <a name="idiasymbolgetthisadjust"></a>IDiaSymbol::get_thisAdjust
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

論理取得`this`調整メソッドの権限を保持します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_thisAdjust (   
   LONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]返します、論理`this`調整メソッドの権限を保持します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
>  戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。  
  
## <a name="remarks"></a>Remarks  
 複数の継承によってメソッド自体が、真を計算する必要があります`this`値のオフセット位置に追加することによって`this`します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
