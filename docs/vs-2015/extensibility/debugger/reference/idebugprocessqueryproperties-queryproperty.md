---
title: IDebugProcessQueryProperties::QueryProperty | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugProcessQueryProperties::QueryProperty
ms.assetid: 9a91707d-a590-44ef-b122-69d9816a7a79
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 72f91d6cf8554567807e958ae9a32b93f9228c8f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62537668"
---
# <a name="idebugprocessquerypropertiesqueryproperty"></a>IDebugProcessQueryProperties::QueryProperty
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このメソッドは、デバッグ プロセスの指定したプロパティ値のクエリを実行します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT QueryProperty(  
   PROCESS_PROPERTY_TYPE  dwPropType,  
   VARIANT               *pvarPropValue);  
```  
  
```csharp  
int QueryProperty(  
   enum_PROCESS_PROPERTY_TYPE dwPropType,  
   out object                 pvarPropValue);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwPropType`  
 [in]クエリを実行プロパティの定義。 次の値があります。  
  
- PROCESS_PROPERTY_COMMAND_LINE = 1  
  
- PROCESS_PROPERTY_CURRENT_DIRECTORY = 2  
  
- PROCESS_PROPERTY_ENVIRONMENT_VARIABLES 3 を =  
  
  `pvarPropValue`  
  [out]プロパティの値。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドが使用されることはほとんどありません。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProcessQueryProperties](../../../extensibility/debugger/reference/idebugprocessqueryproperties.md)
