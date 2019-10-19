---
title: 'IActiveScript:: GetScriptDispatch |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetScriptDispatch
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetScriptDispatch
ms.assetid: 2092ccd4-1f4c-493a-b5b7-077a70ce95ca
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ba53f2eccde18bd5b2d9c609ea680b50cb7261c9
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575761"
---
# <a name="iactivescriptgetscriptdispatch"></a>IActiveScript::GetScriptDispatch
現在実行中のスクリプトに関連付けられているメソッドおよびプロパティの `IDispatch` インターフェイスを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetScriptDispatch(  
    LPCOLESTR pstrItemName  // address of item name  
    IDispatch **ppdisp      // receives IDispatch pointer  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pstrItemName`  
 から呼び出し元が関連付けられているディスパッチオブジェクトを必要とする項目の名前を格納しているバッファーのアドレス。 このパラメーターが `NULL` 場合、ディスパッチオブジェクトには、スクリプトによって定義されたグローバルメソッドとプロパティのすべてのメンバーが含まれます。 ホストは、`IDispatch` インターフェイスと関連付けられた `ITypeInfo` インターフェイスを使用して、スクリプトメソッドを呼び出したり、スクリプト変数を表示および変更したりできます。  
  
 `ppdisp`  
 入出力スクリプトのグローバルメソッドとプロパティに関連付けられたオブジェクトへのポインターを受け取る変数のアドレス。 スクリプトエンジンがこのようなオブジェクトをサポートしていない場合は `NULL` が返されます。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_INVALIDARG`|引数が無効です。|  
|`E_POINTER`|無効なポインターが指定されました。|  
|`E_UNEXPECTED`|この呼び出しは想定されていませんでした (たとえば、スクリプトエンジンがまだ読み込まれていないか、初期化されていません)。|  
|`S_FALSE`|スクリプトエンジンはディスパッチオブジェクトをサポートしていません。`ppdisp` パラメーターが NULL に設定されています。|  
  
## <a name="remarks"></a>Remarks  
 [IActiveScriptParse](../../winscript/reference/iactivescriptparse.md)インターフェイスを呼び出すことによってメソッドとプロパティを追加できるため、このメソッドによって返される `IDispatch` インターフェイスは、新しいメソッドとプロパティを動的にサポートできます。 同様に、`IDispatch::GetTypeInfo` メソッドは、メソッドとプロパティが追加されたときに、新しい一意の `ITypeInfo` インターフェイスを返す必要があります。 ただし、この言語エンジンは、返された前の `ITypeInfo` インターフェイスと互換性がない方法で `IDispatch` インターフェイスを変更することはできません。 これは、たとえば、Dispid が再利用されないことを意味します。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)