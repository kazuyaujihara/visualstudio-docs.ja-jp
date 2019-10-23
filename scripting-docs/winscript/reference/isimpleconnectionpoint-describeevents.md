---
title: ISimpleConnectionPoint::D escribeEvents |Microsoft Docs
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
ms.openlocfilehash: b5000689d588fe3f63ec5408893187bba8d13d63
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571819"
---
# <a name="isimpleconnectionpointdescribeevents"></a>ISimpleConnectionPoint::DescribeEvents
指定されたイベントの範囲内の各イベントの DISPID と名前を返します。  
  
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
 から取得する最初のイベントのインデックス。  
  
 `cEvents`  
 から取得するイベントの数。  
  
 `prgid`  
 入出力イベントの DISPID 値の配列。  
  
 `prgbstr`  
 入出力イベント名の配列。  
  
 `pcEventsFetched`  
 入出力フェッチされたイベントの実際の数。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`S_FALSE`|使用可能な数よりも多くのイベントが要求されました。 使用できないイベントは、DISPID_NULL と NULL BSTR で表されます。|  
|`E_INVALIDARG`|要素をフェッチできませんでした。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、指定されたイベントの範囲内の各イベントの DISPID と名前を返します。  
  
## <a name="see-also"></a>関連項目  
 [ISimpleConnectionPoint インターフェイス](../../winscript/reference/isimpleconnectionpoint-interface.md)