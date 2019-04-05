---
title: IDebugProgram3::ExecuteOnThread |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugProgram3::ExecuteOnThread
ms.assetid: 2f5211e3-7a3f-47bf-9595-dfc8b4895d0d
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cfc64f8ae928b4bb0057a16b8a74c6ddbff588c0
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58974594"
---
# <a name="idebugprogram3executeonthread"></a>IDebugProgram3::ExecuteOnThread
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

デバッガーでプログラムを実行します。 プログラムを実行するときに表示するユーザー スレッドをデバッガーの情報を提供するスレッドが返されます。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT ExecuteOnThread(  
   [in] IDebugThread2* pThread)  
```  
  
```csharp  
int ExecuteOnThread(  
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pThread`  
 [in][IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 デバッガーが停止後に実行を再開できる 3 つのさまざまな方法はあります。  
  
- 実行します。前の手順をキャンセルし、これに、次のブレークポイントまで実行します。  
  
- 手順:いずれかの以前の手順をキャンセルし、新しい手順が完了するまでを実行します。  
  
- 続行するには。再度実行して、古いのいずれかの手順のアクティブなままにします。  
  
  渡されるスレッド`ExecuteOnThread`をキャンセルする手順を決定する場合に便利です。 実行している実行スレッドがわからない場合は、すべての手順をキャンセルします。 スレッドの知識があれば、のみのアクティブ スレッドで手順をキャンセルする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [実行](../../../extensibility/debugger/reference/idebugprogram2-execute.md)   
 [IDebugProgram3](../../../extensibility/debugger/reference/idebugprogram3.md)
