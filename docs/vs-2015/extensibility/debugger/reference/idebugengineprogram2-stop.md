---
title: IDebugEngineProgram2::Stop |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngineProgram2::Stop
helpviewer_keywords:
- IDebugEngineProgram2::Stop
ms.assetid: 6e1c3d56-fb67-4a5b-80f9-8ee5131972bf
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cb74cb2940a91bbc64fa4a06f28d07a828357fc6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58976825"
---
# <a name="idebugengineprogram2stop"></a>IDebugEngineProgram2::Stop
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このプログラムで実行されているすべてのスレッドを停止します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT Stop(   
   void   
);  
```  
  
```csharp  
int Stop();  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 複数のプログラムの環境でこのプログラムをデバッグするときに、このメソッドが呼び出されます。 他のプログラムから stopping イベントが受信したときに、このメソッドは、このプログラムで呼び出されます。 このメソッドの実装を非同期にする必要があります。すべてのスレッドがこのメソッドが戻る前に停止する必要あります。 このメソッドの実装を呼び出す可能性があります、 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)このプログラムのメソッド。  
  
 このメソッドへの応答では、デバッグ イベントは送信されません。  
  
## <a name="see-also"></a>関連項目  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)
