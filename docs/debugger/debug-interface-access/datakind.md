---
title: DataKind |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DataKind enumeration
ms.assetid: b64be708-22d6-4360-99e7-8f4e6b196de7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2a967581a2b5da2354908f6f5d6a2f5a35d7fa1c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2019
ms.locfileid: "55040022"
---
# <a name="datakind"></a>DataKind
データ値の特定のスコープを示します。  
  
## <a name="syntax"></a>構文  
  
```C++  
enum DataKind {   
   DataIsUnknown,  
   DataIsLocal,  
   DataIsStaticLocal,  
   DataIsParam,  
   DataIsObjectPtr,  
   DataIsFileStatic,  
   DataIsGlobal,  
   DataIsMember,  
   DataIsStaticMember,  
   DataIsConstant  
};  
```  
  
## <a name="elements"></a>Elements  
 DataIsUnknown  
 データ シンボルを特定できません。  
  
 DataIsLocal  
 データ項目は、ローカル変数です。  
  
 DataIsStaticLocal  
 データ項目は、静的ローカル変数です。  
  
 DataIsParam  
 データ項目は、正式なパラメーターです。  
  
 DataIsObjectPtr  
 データ項目はオブジェクト ポインター (`this`)。  
  
 DataIsFileStatic  
 データ項目は、ファイル スコープ変数です。  
  
 DataIsGlobal  
 データ項目は、グローバル変数です。  
  
 DataIsMember  
 データ項目は、オブジェクト メンバー変数です。  
  
 DataIsStaticMember  
 データ項目は、クラスの静的変数です。  
  
 DataIsConstant  
 データ項目は、定数値です。  
  
## <a name="remarks"></a>解説  
 この列挙体の値がによって返される、 [idiasymbol::get_datakind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)メソッド。  
  
## <a name="requirements"></a>要件  
 ヘッダー: cvconst.h  
  
## <a name="see-also"></a>関連項目  
 [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)