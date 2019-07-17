---
title: IDebugProcess3::GetHostingProcessLanguage |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProcess3::GetHostingProcessLanguage
helpviewer_keywords:
- IDebugProcess3::GetHostingProcessLanguage
ms.assetid: 52fca002-a9ef-43b1-9192-afbe7bb59ad4
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: bd338443a6cad0a772d3780c4dbf361f2634240c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68202834"
---
# <a name="idebugprocess3gethostingprocesslanguage"></a>IDebugProcess3::GetHostingProcessLanguage
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このメソッドが戻る、`GUID`セットとしてへの呼び出しでこのプロセスの言語を表す[SetHostingProcessLanguage](../../../extensibility/debugger/reference/idebugprocess3-sethostingprocesslanguage.md)します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetHostingProcessLanguage(  
   GUID* pguidLang  
);  
```  
  
```csharp  
int GetHostingProcessLanguage(  
   out Guid pguidLang  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pguidLang`  
 [out]`GUID`このプロセスの言語。 `GUID_NULL` (C++) または`Guid.Empty`(c#)、言語が設定されていないことを意味します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [SetHostingProcessLanguage](../../../extensibility/debugger/reference/idebugprocess3-sethostingprocesslanguage.md)
