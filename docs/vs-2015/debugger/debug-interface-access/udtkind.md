---
title: UdtKind |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- UdtKind enumeration
ms.assetid: 400b59b9-373c-42cb-aae1-570494214328
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 9fb22471cea7cd717b8969682a0e1f643f912150
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977257"
---
# <a name="udtkind"></a>UdtKind
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

さまざまなユーザー定義型 (UDT) をについて説明します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
enum UdtKind {   
   UdtStruct,  
   UdtClass,  
   UdtUnion,  
   UdtInterface  
};  
```  
  
## <a name="elements"></a>Elements  
 UdtStruct  
 UDT は、構造です。  
  
 UdtClass  
 UDT は、クラスです。  
  
 UdtUnion  
 UDT は、共用体です。  
  
 UdtInterface  
 UDT は、インターフェイスです。  
  
## <a name="remarks"></a>Remarks  
 この列挙体の値がによって返される、 [idiasymbol::get_udtkind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)メソッド。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: cvconst.h  
  
## <a name="see-also"></a>関連項目  
 [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)
