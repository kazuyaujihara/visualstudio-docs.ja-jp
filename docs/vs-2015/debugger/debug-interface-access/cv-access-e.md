---
title: CV_access_e |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CV_access_e enumeration
ms.assetid: 33c05d65-abb4-4800-a382-54a3805ea7b0
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1ce5997555b37cf5ab30f091e7124b5025284c0e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58972473"
---
# <a name="cvaccesse"></a>CV_access_e
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

メンバー関数と変数の可視性 (アクセス レベル) のスコープを指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
typedef enum CV_access_e {   
   CV_private   = 1,  
   CV_protected = 2,  
   CV_public    = 3  
} CV_access_e;  
```  
  
## <a name="elements"></a>Elements  
 CV_private  
 メンバーは、プライベート アクセスを持ちます。  
  
 CV_protected  
 メンバーがアクセスを保護してきました。  
  
 CV_public  
 メンバーは、パブリック アクセスを持ちます。  
  
## <a name="remarks"></a>Remarks  
 `friend`アクセス指定子は含まれませんので、通常は、クラスの private と protected の両方の要素にアクセスできる非メンバー関数によって使用されます。 使用して、 [idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)でシンボルを検索するメソッド`SymTagFriend`アクセスします。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: cvconst.h  
  
## <a name="see-also"></a>関連項目  
 [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)   
 [IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)
