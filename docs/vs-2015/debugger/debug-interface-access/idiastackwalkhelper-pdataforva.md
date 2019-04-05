---
title: IDiaStackWalkHelper::pdataForVA |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::pdataByVA method
ms.assetid: fafc38fe-74dc-4726-9a51-eebf3a673d7f
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5af921caa989d7279bb9f52751c452d91045cf3e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58962341"
---
# <a name="idiastackwalkhelperpdataforva"></a>IDiaStackWalkHelper::pdataForVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

仮想アドレスに関連付けられている PDATA データ ブロックを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT pdataForVA(   
   ULONGLONG  va,  
   DWORD      cbData,  
   DWORD*     pcbData,  
   BYTE*      pbData  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `va`  
 [in]取得するデータの仮想アドレスを指定します。  
  
 `cbData`  
 [in] (バイト) を取得するデータのサイズ。  
  
 `pcbData`  
 [out]取得したバイトでは、データの実際のサイズを返します。  
  
 `pbData`  
 [入力、出力]要求されたデータが入力バッファー。 `NULL` にすることはできません。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`指定されたアドレスの PDATA がない場合。 それ以外の場合はエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 PDATA (".pdata"という名前の部分)、コンパイル単位の関数の例外処理に関する情報が含まれています。  
  
 データの量が、呼び出し元に、データの量は使用を要求する必要がないために返される、呼び出し元が認識しています。 そのため、許容される場合は、エラーを返すには、このメソッドの実装は、`pbData`パラメーターが`NULL`します。  
  
## <a name="see-also"></a>関連項目  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
