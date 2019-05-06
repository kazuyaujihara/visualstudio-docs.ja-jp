---
title: IDebugProgram2::Execute |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgram2::Execute
helpviewer_keywords:
- IDebugProgram2::Execute
ms.assetid: f7205ce8-0ac6-4fcd-b6ec-b720b4fcaccf
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f6134c10f30d66011dca5e40c28b6cbe6a7c94ed
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63430551"
---
# <a name="idebugprogram2execute"></a>IDebugProgram2::Execute
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

停止状態からこのプログラムの実行が続行されます。 (ステップ) など、以前の実行状態がオフになって、され、プログラムでは、もう一度実行が開始されます。  
  
> [!NOTE]
> このメソッドは非推奨です。 使用して、 [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md)メソッド代わりにします。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT Execute(  
   void  
);  
```  
  
```csharp  
int Execute();  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 ユーザーは、いくつかその他のプログラムのスレッドを停止状態から実行を起動するときに、このプログラムでこのメソッドが呼び出されます。 ユーザーが選択すると、このメソッドが呼び出されますも、**開始**コマンドから、**デバッグ**IDE のメニュー。 このメソッドの実装を呼び出す可能性があります、[再開](../../../extensibility/debugger/reference/idebugthread2-resume.md)プログラムの現在のスレッドでメソッド。  
  
> [!WARNING]
> 停止イベントまたは直接 (同期) イベントを送信しない[イベント](../../../extensibility/debugger/reference/idebugeventcallback2-event.md); この呼び出しを処理中にそれ以外の場合、デバッガーがハングします。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [イベント](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)
