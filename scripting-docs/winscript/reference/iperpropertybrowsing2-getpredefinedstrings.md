---
title: 'IPerPropertyBrowsing2:: Getpre未定義の文字列 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.GetPredefinedStrings
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::GetPredefinedStrings
ms.assetid: d2fa30f7-a566-4dbd-8b47-ffdc00419771
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 55ade724dd9ee5d59feb9d04c5b525ca839a9cec
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576771"
---
# <a name="iperpropertybrowsing2getpredefinedstrings"></a>IPerPropertyBrowsing2::GetPredefinedStrings
呼び出し元がリストボックスに、このプロパティの可能性のある値を表す文字列ポインターのカウントされた配列を入力できるようにします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetPredefinedStrings(  
   DISPID  dispid,  
   CALPOLESTR*  pCaStrings,  
   CADWORD*  pCaCookies  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dispid`  
 から呼び出し元が文字列リストを要求しているプロパティのディスパッチ識別子。  
  
 `pCaStrings`  
 入出力メソッドによって割り当てられた文字列ポインターの配列の要素数とアドレスを格納する、呼び出し元が割り当てた、カウントされた配列の構造体へのポインター。 メソッドが失敗した場合、メモリは割り当てられず、構造体の内容は未定義になります。  
  
 `pCaCookies`  
 入出力メソッドによって割り当てられた Dword の配列の要素数とアドレスを格納する、呼び出し元が割り当てた、カウントされた配列構造体へのポインター。 メソッドが失敗した場合、メモリは割り当てられず、構造体の内容は未定義になります。  
  
## <a name="return-value"></a>戻り値  
 は、有効な `HRESULT` (通常は `S_OK`) を返します。  
  
## <a name="see-also"></a>関連項目  
 [IPerPropertyBrowsing2 インターフェイス 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)