---
title: IDebugApplication110::CallableWaitForHandles |Microsoft Docs
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
ms.openlocfilehash: ac5482924288e52895398084aa4f5ab44e151a66
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58155369"
---
# <a name="idebugapplication110callablewaitforhandles"></a>IDebugApplication110::CallableWaitForHandles
シグナル状態になる一方で、指定したハンドルのいずれかの間、待機スレッド間の呼び出しをこのスレッドに投稿します。 このメソッドは、デバッガー スレッドから呼び出す必要があります。  
  
> [!IMPORTANT]
>  [IDebugApplication110 インターフェイス](../../winscript/reference/idebugapplication110-interface.md)PDM v11.0 以降によって実装された以降には。 activdbg100.h にあります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT CallableWaitForHandles([in] DWORD handleCount, [in, size_is(handleCount)] const HANDLE* pHandles, [out] DWORD* pIndex);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `handleCount`  
 待機ハンドルの数。  
  
 `pHandles`  
 待機ハンドルのセット。  
  
 `pIndex`  
 HRESULT 値が S_OK をインデックスに`pHandles`ハンドルにシグナル状態にします。  
  
## <a name="see-also"></a>関連項目  
 [IDebugApplication110 インターフェイス](../../winscript/reference/idebugapplication110-interface.md)