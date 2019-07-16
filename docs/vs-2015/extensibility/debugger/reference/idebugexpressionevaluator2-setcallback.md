---
title: IDebugExpressionEvaluator2::SetCallback |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugExpressionEvaluator2::SetCallback
- SetCallback
ms.assetid: 31e3a99e-e784-44a3-8b19-cc5ef31ed546
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8d6f715bb33afe051cdccffbf3219e062b606f57
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68179924"
---
# <a name="idebugexpressionevaluator2setcallback"></a>IDebugExpressionEvaluator2::SetCallback
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

メトリックの設定を読み取るデバッガー エンジン (DE) を使用するコールバック インターフェイスを指定するには、式エバリュエーター (EE) を有効にします。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT SetCallback (  
   IDebugSettingsCallback2* pCallback  
);  
```  
  
```csharp  
int SetCallback (  
   IDebugSettingsCallback2 pCallback  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pCallback`  
 [in]設定のコールバックを使用するインターフェイスです。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、式エバリュエーターは、メトリックの設定の読み取りに使用できるセッション デバッグ マネージャーのインターフェイスを提供します。 メトリックを読み取ります。 へのリモート デバッグで役に立ちますが、[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]コンピューター。  
  
## <a name="example"></a>例  
 次の例のこのメソッドを実装する方法を示しています、 **CEE**を公開するオブジェクト、 [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)インターフェイス。  
  
```cpp#  
HRESULT CEE::SetCallback(IDebugSettingsCallback2* in_pCallback)  
{  
    // precondition  
    INVARIANT( this );  
  
    // function body  
    if (NULL != this->m_LanguageSpecificUseCases.pfSetCallback)  
    {  
        EEDomain::fSetCallback DomainVal =  
        {  
            in_pCallback  
        };  
  
        BOOL bSuccess = (*this->m_LanguageSpecificUseCases.pfSetCallback)(DomainVal);  
        ENSURE( bSuccess );  
    }  
  
    // postcondition  
    INVARIANT( this );  
  
    return S_OK;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)
