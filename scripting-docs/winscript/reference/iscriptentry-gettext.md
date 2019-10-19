---
title: 'IScriptEntry:: GetText |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.GetText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::GetText
ms.assetid: 105b8244-1972-4b39-ac18-965f1f345ef2
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2b25c1667f1df7e0394dd2ebfb0fea452da1b47d
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575404"
---
# <a name="iscriptentrygettext"></a>IScriptEntry::GetText
@No__t_0 スクリプトブロックに対応するテキスト、または `IScriptScriptlet` イベントハンドラーに含まれているソースコードを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetText(  
   BSTR               *pbstr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstr`  
 入出力@No__t_0 スクリプトブロック内のテキスト、または `IScriptScriptlet` イベントハンドラーに含まれているソースコード。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [IScriptEntry インターフェイス](../../winscript/reference/iscriptentry-interface.md)