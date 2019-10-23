---
title: 'IScriptEntry:: GetRange |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.GetRange
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::GetRange
ms.assetid: 3ac18f0a-b470-4f4d-b8f5-2da3fdef74f1
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a6e1b1600c93aa05bbe9669fb57a23a8c9344a1
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575432"
---
# <a name="iscriptentrygetrange"></a>IScriptEntry::GetRange
エントリの開始位置と長さを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetRange(  
   ULONG              *pichMin  
   ULONG              *pcch  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pichMin`  
 入出力スクリプトブロックを指定する `IScriptEntry` オブジェクトの場合、は0を返します。  
  
 関数オブジェクトを指定する `IScriptEntry` オブジェクトの場合は、現在のスクリプトブロック内の関数の開始位置を返します。  
  
 @No__t_0 オブジェクトの場合、は0を返します。  
  
 `pcch`  
 入出力スクリプトブロックを指定する `IScriptEntry` オブジェクトの場合は、テキストの長さを返します。  
  
 関数オブジェクトを指定する `IScriptEntry` オブジェクトの場合は、関数定義の長さを返します。  
  
 @No__t_0 オブジェクトの場合は、エントリの長さを返します。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IScriptEntry インターフェイス](../../winscript/reference/iscriptentry-interface.md)