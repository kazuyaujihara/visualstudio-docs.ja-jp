---
title: 'IActiveScriptSiteDebug:: GetDocumentContextFromPosition |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteDebug.GetDocumentContextFromPosition
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteDebug::GetDocumentContextFromPosition
ms.assetid: ba5f7348-0107-4b12-b949-79a012476cf7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 61bc36b98fee31ced1f3e8e00d084b5dabcd2124
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72570161"
---
# <a name="iactivescriptsitedebuggetdocumentcontextfromposition"></a>IActiveScriptSiteDebug::GetDocumentContextFromPosition
@No__t_0 を委任するために言語エンジンによって使用されます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetDocumentContextFromPosition(  
   DWORD_PTR                dwSourceContext,  
   ULONG                    uCharacterOffset,  
   ULONG                    uNumChars,  
   IDebugDocumentContext**  ppsc  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwSourceContext`  
 から@No__t_0 または `AddScriptlet` に提供されるソースコンテンツ。  
  
 `uCharacterOffset`  
 からスクリプトブロックまたはスクリプトレットの開始位置を基準とした文字オフセット。  
  
 `uNumChars`  
 からこのコンテキストの文字数。  
  
 `ppsc`  
 入出力この文字位置の範囲に対応するドキュメントコンテキスト。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 言語エンジンは、このメソッドを使用して `IDebugCodeContext::GetSourceContext` を委任します。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSiteDebug インターフェイス](../../winscript/reference/iactivescriptsitedebug-interface.md)