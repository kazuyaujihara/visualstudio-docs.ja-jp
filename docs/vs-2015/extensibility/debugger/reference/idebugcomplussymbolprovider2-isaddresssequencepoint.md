---
title: IDebugComPlusSymbolProvider2::IsAddressSequencePoint |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugComPlusSymbolProvider2::IsAddressSequencePoint
- IsAddressSequencePoint
ms.assetid: 89b27c57-5295-428b-8229-a402500d8cd3
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 761264f57ba0eb0775159f3cc2c3385228723eb2
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977271"
---
# <a name="idebugcomplussymbolprovider2isaddresssequencepoint"></a>IDebugComPlusSymbolProvider2::IsAddressSequencePoint
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

指定されたデバッグ アドレスがシーケンス ポイントであるかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT IsAddressSequencePoint(  
   IDebugAddress* pAddress  
);  
```  
  
```csharp  
int IsAddressSequencePoint(  
   IDebugAddress pAddress  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pAddress`  
 [in]デバッグで表されるアドレス、 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)インターフェイス。  
  
## <a name="return-value"></a>戻り値  
 デバッグ アドレスがシーケンス ポイントの場合を返します`S_OK`。 それ以外を返します`S_FALSE`します。  
  
## <a name="example"></a>例  
 次の例では、このメソッドを実装する方法を示しています、 **CDebugSymbolProvider**を公開するオブジェクト、 [IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md)インターフェイス。  
  
```cpp#  
HRESULT CDebugSymbolProvider::IsAddressSequencePoint(  
    IDebugAddress* pAddress  
)  
{  
    HRESULT hr = S_OK;  
    CDEBUG_ADDRESS address;  
    CComPtr<CModule> pModule;  
  
    METHOD_ENTRY( CDebugSymbolProvider::LoadSymbol );  
  
    IfFalseGo( pAddress, E_INVALIDARG );  
  
    IfFailGo( pAddress->GetAddress( &address ) );  
  
    ASSERT(address.addr.dwKind == ADDRESS_KIND_METADATA_METHOD);  
    IfFalseGo( address.addr.dwKind == ADDRESS_KIND_METADATA_METHOD, S_FALSE );  
  
    IfFailGo( GetModule( address.GetModule(), &pModule) );  
  
    if (!pModule->IsSequencePoint( address.addr.addr.addrMethod.tokMethod,  
                                   address.addr.addr.addrMethod.dwVersion,  
                                   address.addr.addr.addrMethod.dwOffset ))  
    {  
  
        // S_FALSE indicates this is not a sequence point  
  
        hr = S_FALSE;  
    }  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::LoadSymbol, hr );  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md)
