---
title: IDebugExceptionEvent2::PassToDebuggee |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugExceptionEvent2::PassToDebuggee
helpviewer_keywords:
- IDebugExceptionEvent2::PassToDebuggee
ms.assetid: a20d0f0b-2ca0-4437-bd22-9213c81d2738
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ecc7eb3830522cdee0022f4193482daab3780230
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68150394"
---
# <a name="idebugexceptionevent2passtodebuggee"></a>IDebugExceptionEvent2::PassToDebuggee
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

例外を破棄する場合または実行の再開時にデバッグ中のプログラムを例外を渡す必要があるかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT PassToDebuggee(  
   BOOL fPass  
);  
```  
  
```csharp  
int PassToDebuggee(  
   int fPass  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fPass`  
 [in]0 以外の場合 (`TRUE`) 場合は、例外は、実行の再開時にデバッグ中のプログラムまたは 0 渡す必要があります (`FALSE`) 場合は、例外を破棄する必要があります。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドを呼び出すことも、デバッグ中のプログラムで実行するためのコードは実際には発生しません。 呼び出しは、次のコード実行の状態を設定するだけです。 たとえば、呼び出し、 [CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)メソッドが返す可能性があります`S_OK`で、 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)します。`dwState` フィールドに設定`EXCEPTION_STOP_SECOND_CHANCE`します。  
  
 IDE が表示される、 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)イベントと呼び出し、[続行](../../../extensibility/debugger/reference/idebugprogram2-continue.md)メソッド。 デバッグ エンジン (DE) は大文字と小文字の場合を処理するために既定の動作が必要、`PassToDebuggee`メソッドは呼び出されません。  
  
## <a name="see-also"></a>関連項目  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)   
 [Continue](../../../extensibility/debugger/reference/idebugprogram2-continue.md)
