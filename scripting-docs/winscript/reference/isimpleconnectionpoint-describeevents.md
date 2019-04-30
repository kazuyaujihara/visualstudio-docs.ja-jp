---
title: ISimpleConnectionPoint::DescribeEvents |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISimpleConnectionPoint.DescribeEvents
apilocation:
- pdm.dll
helpviewer_keywords:
- ISimpleConnectionPoint::DescribeEvents
ms.assetid: 659ea05f-d41e-424a-bb38-df7672b2d135
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1b5824f945ad25f177fc169b58157377bf53bcce
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62786420"
---
# <a name="isimpleconnectionpointdescribeevents"></a>ISimpleConnectionPoint::DescribeEvents
イベントの指定した範囲内で、DISPID と各イベントの名前を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT DescribeEvents(  
   ULONG    iEvent,  
   ULONG    cEvents,  
   DISPID*  prgid,  
   BSTR*    prgbstr,  
   ULONG*   pcEventsFetched  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `iEvent`  
 [in]取得する最初のイベントのインデックス。  
  
 `cEvents`  
 [in]取得するイベントの数。  
  
 `prgid`  
 [out]イベントの DISPID 値の配列。  
  
 `prgbstr`  
 [out]イベント名の配列。  
  
 `pcEventsFetched`  
 [out]実際にフェッチされるイベントの数。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`S_FALSE`|使用可能なより多くのイベントは要求されました。 使用できないイベントは、DISPID_NULL と null BSTR で表されます。|  
|`E_INVALIDARG`|要素はフェッチされませんでした。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、イベントの指定した範囲内で、DISPID と各イベントの名前を返します。  
  
## <a name="see-also"></a>関連項目  
 [ISimpleConnectionPoint インターフェイス](../../winscript/reference/isimpleconnectionpoint-interface.md)