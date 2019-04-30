---
title: IActiveScriptAuthor::GetLanguageFlags |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.GetLanguageFlags
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::GetLanguageFlags
ms.assetid: eb244452-62f7-4a73-b48f-1aa05cbcc32d
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d9f1a68db05ac0d909108ce77587ae4b071c9a2b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62935472"
---
# <a name="iactivescriptauthorgetlanguageflags"></a>IActiveScriptAuthor::GetLanguageFlags
言語情報を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetLanguageFlags(  
   DWORD              *pgrfasa  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pgrfasa`  
 [out]このフラグは、言語情報が含まれます。 次の値の組み合わせになります。  
  
|定数|値|説明|  
|--------------|-----------|-----------------|  
|fasaPreferInternalHandler|0x0001|言語は、エンジンは、アプリケーションではなくを作成、スクリプトによってスクリプト イベント ハンドラーの作成を優先します。|  
|fasaSupportInternalHandler|0x0002|言語は、エンジンを作成するスクリプトによって作成されたスクリプトのイベント ハンドラーをサポートしています。|  
|fasaCaseSensitive|0x0004|スクリプト言語は大文字小文字を区別します。|  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 エンジンを作成するスクリプトは、イベント ハンドラーを管理している場合、アプリケーションを呼び出す必要があります`CreateChildHandler`から、`IScriptEntry`オブジェクト。 これを作成、`IScriptScriptlet`イベント ハンドラーに対応するオブジェクト。 エンジンは、スクリプトのエントリにも、イベント ハンドラーを追加します。 イベント ハンドラーは、指定した署名情報を含む空の関数です。  
  
 呼び出す必要がありますが、アプリケーションでは、イベント ハンドラーが管理する場合、`CreateChildHandler`から、`IScriptNode`イベントのハンドラー スクリプトレットを表すオブジェクト。 これを作成、`IScriptScriptlet`イベント ハンドラー スクリプトレットに関連付けられているオブジェクト。 アプリケーションがイベントとして空の関数を追加するハンドラーを新しいまたは既存の`IScriptEntry`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptAuthor インターフェイス](../../winscript/reference/iactivescriptauthor-interface.md)