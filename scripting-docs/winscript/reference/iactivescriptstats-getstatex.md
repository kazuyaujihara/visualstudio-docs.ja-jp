---
title: IActiveScriptStats::GetStatEx |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptStats.GetStatEx
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptStats::GetStatEx
ms.assetid: f526f51d-8ab5-49ef-a8f7-ae0ac1cb46e4
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3e5f25887d8fdd5b5fb774cc2e8619c1a93432c1
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63442779"
---
# <a name="iactivescriptstatsgetstatex"></a>IActiveScriptStats::GetStatEx
カスタム スクリプトの統計を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetStatEx(  
   REFGUID  guid,  
   ULONG*   pluHi,  
   ULONG*   pluLo  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `guid`  
 [in]返される統計情報を指定します。 セマンティクスの統計情報に対応する特定の GUID 全体が定義されているエンジン。  
  
 `pluHi`  
 [out]統計情報を表す 64 ビット符号なし整数の上位 32 ビット。  
  
 `pluLo`  
 [out]統計情報を表す 64 ビット符号なし整数の下位 32 ビット。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_NOTIMPL`|メソッドが実装されていません。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、カスタム ホストに意味のある統計情報を返すカスタム スクリプト エンジンを使用します。  
  
> [!NOTE]
> このメソッドは現在実装されていません。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptStats::GetStat](../../winscript/reference/iactivescriptstats-getstat.md)   
 [IActiveScriptStats インターフェイス](../../winscript/reference/iactivescriptstats-interface.md)