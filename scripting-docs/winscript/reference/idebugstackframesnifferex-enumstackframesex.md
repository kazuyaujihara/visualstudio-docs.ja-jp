---
title: 'IDebugStackFrameSnifferEx:: Enumstackフレーム Sex |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugStackFrameSnifferEx.EnumStackFramesEx
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugStackFrameSnifferEx::EnumStackFramesEx
ms.assetid: b656b581-aff0-4984-8d8a-a1c7a8e6558a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6a4062e7c0a9b3a82578daffa2ab7ef7e9ba614d
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576705"
---
# <a name="idebugstackframesnifferexenumstackframesex"></a>IDebugStackFrameSnifferEx::EnumStackFramesEx
現在のスレッドのスタックフレームの列挙子を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT EnumStackFramesEx(  
   DWORD_PTR                dwSpMin,  
   IEnumDebugStackFrames**  ppedsf  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwSpMin`  
 からスタックフレームを列挙するための下限アドレス。  
  
 `ppedsf`  
 入出力現在のスレッドのスタックフレームの列挙子。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 スタックフレーム列挙子は、最後にプッシュされたフレームを使用して、スタックの一番上から始まるフレームを返します。 列挙子には、`dwSpMin` 以上のアドレスを持つスタックフレームだけが含まれます。  
  
## <a name="see-also"></a>関連項目  
 [IDebugStackFrameSnifferEx インターフェイス](../../winscript/reference/idebugstackframesnifferex-interface.md)