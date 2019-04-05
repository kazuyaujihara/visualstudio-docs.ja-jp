---
title: IPropertyProxyEESide::CreateReplacementObject |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide::CreateReplacementObject
helpviewer_keywords:
- IPropertyProxyEESide::CreateReplacementObject
ms.assetid: 0cfe79b8-c3f1-48b0-a225-e39dee2c92fe
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c3a21e640d6661f8066609bdc344299ccbd63d52
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977987"
---
# <a name="ipropertyproxyeesidecreatereplacementobject"></a>IPropertyProxyEESide::CreateReplacementObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

式エバリュエーター (EE) に固有のデータ オブジェクトのコピーを作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT CreateReplacementObject(  
   IEEDataStorage*  dataIn,  
   IEEDataStorage** dataOut  
);  
```  
  
```csharp  
int CreateReplacementObject(  
   IEEDataStorage     dataIn,  
   out IEEDataStorage dataOut  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dataIn`  
 [in][IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)データのコピーを保持しているオブジェクト。  
  
 `dataOut`  
 [out]新しいを返します`IEEDataStorage`オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドが指定された、 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)バイトの配列を表すオブジェクト。 この入力方向のデータ オブジェクトは通常、EE によって実装されていません。 ただし、このメソッドによって返されるオブジェクトは、EE 実装できるように、EE によって実装は常に、`IEEDataStorage`でどのようなクラスが必要なインターフェイスです。  
  
 データが受信によって提供されることに注意してください。`IEEDataStorage`オブジェクトは、送信で同じデータである必要があります`IEEDataStorage`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
