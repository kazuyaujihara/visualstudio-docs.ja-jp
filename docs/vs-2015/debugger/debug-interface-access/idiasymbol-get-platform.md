---
title: Idiasymbol::get_platform |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_platform method
ms.assetid: dff1c1eb-bcb2-4275-bb07-f2fdc076d6fb
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c44603a767903e71103107fab6f8f041e7946902
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64783618"
---
# <a name="idiasymbolgetplatform"></a>IDiaSymbol::get_platform
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

コンパイル単位のコンパイル対象のプラットフォームの種類を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_platform (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]値を返します、 [CV_CPU_TYPE_e 列挙型](../../debugger/debug-interface-access/cv-cpu-type-e.md)コンパイル単位がコンパイルされたのプラットフォームを指定する列挙値を入力します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
> 戻り値`S_FALSE`プロパティがシンボルを使用できないことを意味します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [CV_CPU_TYPE_e 列挙型](../../debugger/debug-interface-access/cv-cpu-type-e.md)
