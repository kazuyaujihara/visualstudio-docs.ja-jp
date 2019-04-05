---
title: IDebugTypeFieldBuilder::CreatePrimitive |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- CreatePrimitive
- IDebugTypeFieldBuilder::CreatePrimitive
ms.assetid: 512c6ff0-97c5-409f-939f-4cc969bc4bb9
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 5b3119f6fda1b178232c668951b0a5c15004b119
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973883"
---
# <a name="idebugtypefieldbuildercreateprimitive"></a>IDebugTypeFieldBuilder::CreatePrimitive
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

プリミティブ型を表すオブジェクトを作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT CreatePrimitive (  
   DWORD          dwElementType,  
   IDebugField ** pTypeField  
);  
```  
  
```csharp  
int CreatePrimitive (  
   uint            dwElementType,  
   out IDebugField pTypeField  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwElementType`  
 [in]値を[CorElementType 列挙型](/dotnet/framework/unmanaged-api/metadata/corelementtype-enumeration)プリミティブ型を表します。  
  
 `pTypeField`  
 [out]新しい種類の IDebugField インターフェイスを返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugTypeFieldBuilder](../../../extensibility/debugger/reference/idebugtypefieldbuilder.md)
