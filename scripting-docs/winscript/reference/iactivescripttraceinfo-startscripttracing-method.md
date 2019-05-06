---
title: Iactivescripttraceinfo::startscripttracing メソッド |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 90fac5ed-ce15-49b7-a6f1-605ede6f34e2
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b87971e1fd2e484aa54ff4de56ee56e00b19b1e6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62991193"
---
# <a name="iactivescripttraceinfostartscripttracing-method"></a>IActiveScriptTraceInfo::StartScriptTracing メソッド
スクリプト トレースを開始します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT StartScriptTracing(     [in] IActiveScriptSiteTraceInfo * pSiteTraceInfo,     [in] GUID guidContextID );   
```  
  
#### <a name="parameters"></a>パラメーター  
 `pSiteTraceInfo`  
 ホストの IActiveScriptSiteTraceInfo へのポインター。  
  
 `guidContextId`  
 コンテキストの GUID です。  
  
## <a name="return-value"></a>戻り値  
 このメソッドの戻り値以下のとおりです。  
  
1. S_OK を返します。成功。  
  
2. E_POINTER: `pSiteTraceInfo` NULL ポインターです。  
  
3. E_NOTIMPL:実装されていません。