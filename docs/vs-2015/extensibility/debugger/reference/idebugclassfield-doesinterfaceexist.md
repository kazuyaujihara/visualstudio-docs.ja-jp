---
title: IDebugClassField::DoesInterfaceExist |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugClassField::DoesInterfaceExist
helpviewer_keywords:
- IDebugClassField::DoesInterfaceExist method
ms.assetid: cc0c8642-1a76-4fda-a309-7018a34883c9
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9f71346c1b69729ae54ef0d33be4149e7000316c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58975042"
---
# <a name="idebugclassfielddoesinterfaceexist"></a>IDebugClassField::DoesInterfaceExist
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

特定のインターフェイスは、クラスで定義されているかどうかを決定します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT DoesInterfaceExist(   
   LPCOLESTR pszInterfaceName  
);  
```  
  
```csharp  
int DoesInterfaceExist(  
   [In] string pszInterfaceName  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszInterfaceName`  
 [in]検索するインターフェイス名を含む文字列。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK を返します、S_FALSE を返す場合は、インターフェイスは存在しません。それ以外の場合、エラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 有効で、このメソッドは、すべてのインターフェイスの列挙体を取得し、一致するインターフェイスの一覧を検索します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
