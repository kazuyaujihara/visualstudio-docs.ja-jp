---
title: IDebugEngine2::CauseBreak |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngine2::CauseBreak
helpviewer_keywords:
- IDebugEngine2::CauseBreak
ms.assetid: 17fe4698-b04e-4798-8412-80e0da60c387
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2b6e52e4885a61c3fe04fff5bdcca08fd00cf460
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58976198"
---
# <a name="idebugengine2causebreak"></a>IDebugEngine2::CauseBreak
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

すべてのプログラムによってこのデバッグ エンジン (DE)、次回の実行を停止するデバッグ中の要求を実行すると、スレッドの 1 つ試行します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT CauseBreak(   
   void   
);  
```  
  
```csharp  
int CauseBreak();  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドは非同期: [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)次に、プログラムはこのメソッドが呼び出された後に実行しようとしたときにイベントが送信されます。  
  
## <a name="see-also"></a>関連項目  
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
