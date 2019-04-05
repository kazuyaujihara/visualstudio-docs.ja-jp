---
title: IEnumDebugAddresses::Next |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumDebugAddresses::Next
helpviewer_keywords:
- IEnumDebugAddresses::Next method
ms.assetid: 941e4be7-858d-433a-9259-18d0d017be9e
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1275fe1f1daaa8bd512251480e7c87a71512523e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58962738"
---
# <a name="ienumdebugaddressesnext"></a>IEnumDebugAddresses::Next
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このメソッドは、列挙体から次の要素のセットを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT Next(  
   ULONG           celt,  
   IDebugAddress** rgelt,  
   ULONG*          pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint            celt,  
   IDebugAddress[] rgelt,  
   ref uint        pceltFetched  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]取得する要素の数。 最大サイズを指定します、`rgelt`配列。  
  
 `rgelt`  
 [入力、出力]配列[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)情報を格納する要素。  
  
 `pceltFetched`  
 [out]実際に返される要素の数を返します`rgelt`します。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`返される可能性があります、要求された要素数よりも少ない場合、それ以外の場合、エラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)
