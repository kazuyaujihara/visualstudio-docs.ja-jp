---
title: Idiasymbol::get_isltcg |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isLTCG method
ms.assetid: 5f7f05b8-6b71-4958-9e1e-e4924ef9c59b
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: fa9a7666fb233ac54db8fc3bfd50b055e7bf937d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58972677"
---
# <a name="idiasymbolgetisltcg"></a>IDiaSymbol::get_isLTCG
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

指定するフラグを取得するかどうか、[コンパイル単位](../../debugger/debug-interface-access/compiland.md)リンカー スイッチにリンクされている[/LTCG (リンク時コード生成)](http://msdn.microsoft.com/library/788c6f52-fdb8-40c2-90af-4026ea2cf2e2)、プログラム全体の最適化を支援します。 このスイッチは、マネージ コードにのみ適用されます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT get_iSLTCG(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 pFlag  
 [out]返します`TRUE`場合、 `compiland` /LTCG リンカー スイッチを使用してリンクされました。 それ以外の場合、`FALSE`します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
>  戻り値`S_FALSE`プロパティがシンボルを使用できないことを意味します。  
  
## <a name="requirements"></a>必要条件  
  
|必要条件|説明|  
|-----------------|-----------------|  
|ヘッダー:|Dia2.h|  
|バージョン:|DIA SDK バージョン 8.0|  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
