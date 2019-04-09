---
title: IDebugCustomAttribute::GetName |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugCustomAttribute::GetName
helpviewer_keywords:
- IDebugCustomAttribute::GetName
ms.assetid: ba509cc5-5816-4925-a094-4c72d88c360c
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4463fc4f9d321b26487e885255843a7acd945f76
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58974979"
---
# <a name="idebugcustomattributegetname"></a>IDebugCustomAttribute::GetName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

カスタム属性の名前を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetName(   
   BSTR* bstrName  
);  
```  
  
```csharp  
int GetName(  
   out string bstrName  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `bstrName`  
 [out]カスタム属性の名前を含む文字列を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドによって返される名前付き属性を宣言するために使用するクラスの名前に対応します。 カスタム属性クラス自体の名前に対応して C# では、宣言で使用されるときにカスタム属性名から削除する"Attribute"というサフィックスとしてこの可能性がありますも一致しません。  
  
## <a name="see-also"></a>関連項目  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)
