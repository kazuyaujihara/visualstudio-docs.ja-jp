---
title: 'IActiveScriptSite:: GetItemInfo |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.GetItemInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_GetItemInfo
ms.assetid: f859ed3b-02c1-4924-99f8-5f5bf1bf8405
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3c0458f42466a264c30a440b1b14a028a2457f12
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72570917"
---
# <a name="iactivescriptsitegetiteminfo"></a>IActiveScriptSite::GetItemInfo
[IActiveScript:: AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md)メソッドを使用して追加された項目に関する情報をスクリプトエンジンが取得できるようにします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetItemInfo(  
    LPCOLESTR pstrName,     // address of item name  
    DWORD dwReturnMask,     // bit mask for information retrieval  
    IUnknown **ppunkItem,   // address of pointer to item's IUnknown  
    ITypeInfo **ppTypeInfo  // address of pointer to item's ITypeInfo  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pstrName`  
 から[IActiveScript:: AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md)メソッドで指定された、項目に関連付けられている名前。  
  
 `dwReturnMask`  
 から項目に関する情報を返すビットマスク。 いくつかの戻り値のパラメーター (`ITypeInfo` など) の読み込みまたは生成にかなりの時間がかかるため、スクリプトエンジンはできるだけ最小限の情報を要求する必要があります。 は、次の値の組み合わせにすることができます。  
  
|[値]|説明|  
|-----------|-------------|  
|SCRIPTINFO_IUNKNOWN|この項目の `IUnknown` インターフェイスを返します。|  
|SCRIPTINFO_ITYPEINFO|この項目の `ITypeInfo` インターフェイスを返します。|  
  
 `ppunkItem`  
 入出力指定した項目に関連付けられている `IUnknown` インターフェイスへのポインターを受け取る変数のアドレス。 スクリプトエンジンは、`IUnknown::QueryInterface` メソッドを使用して、項目の `IDispatch` インターフェイスを取得できます。 @No__t_0 に SCRIPTINFO_IUNKNOWN 値が含まれていない場合、このパラメーターは NULL を受け取ります。 また、項目名に関連付けられたオブジェクトがない場合は NULL を受け取ります。このメカニズムは、 [IActiveScript:: AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md)メソッドで設定された SCRIPTITEM_CODEONLY フラグを使用して名前付き項目を追加した場合に、単純なクラスを作成するために使用されます。  
  
 `ppTypeInfo`  
 入出力項目に関連付けられている `ITypeInfo` インターフェイスへのポインターを受け取る変数のアドレス。 @No__t_0 に SCRIPTINFO_ITYPEINFO 値が含まれていない場合、またはこの項目に対して型情報を使用できない場合、このパラメーターは NULL を受け取ります。 型情報を使用できない場合、オブジェクトはイベントをソースにすることができず、`IDispatch::GetIDsOfNames` メソッドを使用して名前のバインドを実現する必要があります。 オブジェクトが複数のインターフェイスとイベントインターフェイスをサポートする可能性があるため、取得される `ITypeInfo` インターフェイスは、項目のコクラス (TKIND_COCLASS) について説明します。 項目が `IProvideMultipleTypeInfo` インターフェイスをサポートしている場合、取得される `ITypeInfo` インターフェイスは、`IProvideMultipleTypeInfo::GetInfoOfIndex` メソッドを使用して取得されるインデックスゼロ `ITypeInfo` と同じになります。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_INVALIDARG`|引数が無効です。|  
|`E_POINTER`|無効なポインターが指定されました。|  
|`TYPE_E_ELEMENTNOTFOUND`|指定された名前の項目が見つかりませんでした。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、`dwReturnMask` パラメーターによって示される情報のみを取得します。これにより、パフォーマンスが向上します。 たとえば、項目に対して `ITypeInfo` インターフェイスが不要な場合、`dwReturnMask` では指定されていません。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)