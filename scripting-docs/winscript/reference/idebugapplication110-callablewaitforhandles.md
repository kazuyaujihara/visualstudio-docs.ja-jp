---
title: 'IDebugApplication110:: CallableWaitForHandles |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplication110::CallableWaitForHandles
ms.assetid: 02e79b60-0d67-47f9-bf78-b65a02c9c014
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 22af0e9dcf548bbd2f0f8c179b4889d5294eb284
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575085"
---
# <a name="idebugapplication110callablewaitforhandles"></a>IDebugApplication110::CallableWaitForHandles
指定されたハンドルのいずれかがシグナル状態になるまで待機し、スレッド間の呼び出しをこのスレッドにポストすることを許可します。 このメソッドは、デバッガースレッドから呼び出す必要があります。  
  
> [!IMPORTANT]
> [IDebugApplication110 インターフェイス](../../winscript/reference/idebugapplication110-interface.md)は、PDM version 11.0 以降で実装されています。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT CallableWaitForHandles([in] DWORD handleCount, [in, size_is(handleCount)] const HANDLE* pHandles, [out] DWORD* pIndex);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `handleCount`  
 待機するハンドルの数。  
  
 `pHandles`  
 待機するハンドルのセット。  
  
 `pIndex`  
 HRESULT 値が S_OK の場合、シグナル状態になったハンドルの `pHandles` のインデックス。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplication110 インターフェイス](../../winscript/reference/idebugapplication110-interface.md)