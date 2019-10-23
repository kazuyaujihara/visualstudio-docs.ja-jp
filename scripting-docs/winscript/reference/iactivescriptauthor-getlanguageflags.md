---
title: 'IActiveScriptAuthor:: Get言語 Flags |Microsoft Docs'
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
ms.openlocfilehash: 68da16513050bd87642be2c96212a330a0916608
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576196"
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
 入出力言語情報を含むフラグ。 は、次の値の組み合わせにすることができます。  
  
|定数|[値]|説明|  
|--------------|-----------|-----------------|  
|fasaPreferInternalHandler|0x0001|この言語では、アプリケーションではなくスクリプト作成エンジンによって、スクリプトイベントハンドラーの作成が優先されます。|  
|fasaSupportInternalHandler|0x0002|この言語では、スクリプト作成エンジンによって作成されたスクリプトイベントハンドラーがサポートされています。|  
|fasaCaseSensitive|0x0004|スクリプト言語では大文字と小文字が区別されます。|  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 スクリプト作成エンジンがイベントハンドラーを管理する場合、アプリケーションは `IScriptEntry` オブジェクトから `CreateChildHandler` を呼び出す必要があります。 これにより、イベントハンドラーに対応する `IScriptScriptlet` オブジェクトが作成されます。 また、エンジンは、スクリプトエントリにイベントハンドラーを追加します。 イベントハンドラーは、指定されたシグネチャ情報を格納する空の関数です。  
  
 アプリケーションでイベントハンドラーを管理する場合は、イベントハンドラーのスクリプトレットを表す `IScriptNode` オブジェクトから `CreateChildHandler` を呼び出す必要があります。 これにより、イベントハンドラーのスクリプトレットに関連付けられた `IScriptScriptlet` オブジェクトが作成されます。 また、アプリケーションでは、新規または既存の `IScriptEntry` オブジェクトに、イベントハンドラーとして空の関数を追加する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptAuthor インターフェイス](../../winscript/reference/iactivescriptauthor-interface.md)