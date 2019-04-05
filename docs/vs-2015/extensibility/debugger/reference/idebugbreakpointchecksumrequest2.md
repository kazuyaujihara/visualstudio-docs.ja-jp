---
title: IDebugBreakpointChecksumRequest2 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugBreakpointChecksumRequest2 interface
ms.assetid: 9cfdbca5-052c-48e9-8411-e2e9e4065d00
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9d06656ba05c3356d9f2a148045adbf4538c5ae5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58975043"
---
# <a name="idebugbreakpointchecksumrequest2"></a>IDebugBreakpointChecksumRequest2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

ブレークポイント要求のチェックサムをドキュメントを表します。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugBreakpointChecksumRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 によって実装される、[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]デバッグ パッケージ化とデバッグ エンジンで使用します。  
  
## <a name="methods"></a>メソッド  
 次の表は、メソッドの`IDebugBreakpointChecksumRequest2`します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetChecksum](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2-getchecksum.md)|使用するチェックサム アルゴリズムの一意の識別子を指定されたブレークポイント要求のドキュメントのチェックサムを取得します。|  
|[IsChecksumEnabled](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2-ischecksumenabled.md)|このドキュメントのチェックサムが有効になっているかどうかを決定します。|  
  
## <a name="requirements"></a>必要条件  
 ヘッダー:Msdbg.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll
