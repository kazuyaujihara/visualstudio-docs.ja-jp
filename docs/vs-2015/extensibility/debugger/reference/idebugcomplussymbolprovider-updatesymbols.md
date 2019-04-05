---
title: IDebugComPlusSymbolProvider::UpdateSymbols |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- UpdateSymbols
- IDebugComPlusSymbolProvider::UpdateSymbols
ms.assetid: d530f6f1-4af2-454b-bab0-02478a8fe81e
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b208cadc8264bf3ddbd30d9316b9f0d5a7050b50
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58972826"
---
# <a name="idebugcomplussymbolproviderupdatesymbols"></a>IDebugComPlusSymbolProvider::UpdateSymbols
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

指定したデータ ストリームからメモリにデバッグ シンボルを更新します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT UpdateSymbols (  
   ULONG32  ulAppDomainID,  
   GUID     guidModule,  
   IStream* pUpdateStream  
);  
```  
  
```csharp  
int UpdateSymbols (  
   uint    ulAppDomainID,  
   Guid    guidModule,  
   IStream pUpdateStream  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ulAppDomainID`  
 [in]アプリケーション ドメインの識別子。  
  
 `guidModule`  
 [in]モジュールの一意の識別子。  
  
 `pUpdateStream`  
 [in]更新されたデバッグ シンボルが含まれるデータ ストリーム。  
  
## <a name="example"></a>例  
 次の例では、このメソッドを実装する方法を示しています、 **CDebugSymbolProvider**を公開するオブジェクト、 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)インターフェイス。  
  
```cpp#  
HRESULT CDebugSymbolProvider::UpdateSymbols(  
    ULONG32 ulAppDomainID,  
    GUID guidModule,  
    IStream* pUpdateStream  
)  
{  
    ASSERT(!"Use UpdateSymbols2 on IDebugENCSymbolProvider2");  
    return E_NOTIMPL;  
}  
  
HRESULT CDebugSymbolProvider::UpdateSymbols2(  
    ULONG32 ulAppDomainID,  
    GUID guidModule,  
    IStream* pUpdateStream,  
    LINEDELTA* pDeltaLines,  
    ULONG cDeltaLines  
)  
{  
    HRESULT hr = S_OK;  
    CComPtr<CModule> pModule;  
    Module_ID idModule(ulAppDomainID, guidModule);  
  
    METHOD_ENTRY( CDebugSymbolProvider::UpdateSymbols );  
  
    IfFailGo( GetModule( idModule, &pModule ) );  
    IfFailGo( pModule->UpdateSymbols( pUpdateStream, pDeltaLines, cDeltaLines ) );  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::UpdateSymbols, hr );  
  
    return hr;  
}  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)
