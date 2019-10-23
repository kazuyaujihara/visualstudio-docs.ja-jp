---
title: 'IActiveScriptSiteDebug32:: GetDocumentContextFromPosition |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53348dff-35a6-4303-b263-90c10af06bf3
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: 7acbe2a5741fa94ac42470a85803d1720e0a8fa1
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574845"
---
# <a name="iactivescriptsitedebug32getdocumentcontextfromposition"></a>IActiveScriptSiteDebug32:: GetDocumentContextFromPosition
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
 [IActiveScriptSiteDebug32 インターフェイス](../../winscript/reference/iactivescriptsitedebug32-interface.md)