---
title: IDebugProperty2::GetMemoryContext |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProperty2::GetMemoryContext
helpviewer_keywords:
- IDebugProperty2::GetMemoryContext
ms.assetid: 91793d25-790f-4881-a5c0-d0458e534514
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a3ad83bfe36f468dd0e2d7d040c188fd69970a82
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68193493"
---
# <a name="idebugproperty2getmemorycontext"></a>IDebugProperty2::GetMemoryContext
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

プロパティの値のメモリのコンテキストを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetMemoryContext (   
   IDebugMemoryContext2** ppMemory  
);  
```  
  
```csharp  
int GetMemoryContext(  
   out IDebugMemoryContext2 ppMemory  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppMemory`  
 [out]返します、 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)このプロパティに関連付けられているメモリを表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`; エラー コードを返します。 返します`S_GETMEMORYCONTEXT_NO_MEMORY_CONTEXT`を取得するメモリのコンテキストがない場合。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
