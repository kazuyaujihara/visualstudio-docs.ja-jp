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
ms.openlocfilehash: 824d60ef0f17012524f9d0150a90ccd9efcfb3a9
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58150960"
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
  
1.  S_OK を返します。成功。  
  
2.  E_POINTER: `pSiteTraceInfo` NULL ポインターです。  
  
3.  E_NOTIMPL:実装されていません。