---
title: Idiasymbol::get_targetvirtualaddress |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_targetVirtualAddress method
ms.assetid: a0a5ce72-95f8-443e-bb4b-8c21194faad0
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 36bee874711920d50737962f716e94e6fefd6205
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58974663"
---
# <a name="idiasymbolgettargetvirtualaddress"></a>IDiaSymbol::get_targetVirtualAddress
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

サンク ターゲットの仮想アドレス (VA) を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_targetVirtualAddress (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]サンク ターゲットの VA を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
>  戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。  
  
## <a name="remarks"></a>Remarks  
 このプロパティは有効な場合にのみとしてシンボルを[SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)の値`SymTagThunk`します。  
  
 「サンク」は、32 ビット メモリ アドレス空間 (フラットのアドレス空間とも呼ばれます) と (セグメント化されたアドレス空間と呼ばれます)、16 ビットのアドレス空間を変換するコードです。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 列挙型](../../debugger/debug-interface-access/symtagenum.md)
