---
title: 'IJsDebugProcess:: CreateBreakPoint ポイントメソッド |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugProcess.CreateBreakPoint
apilocation:
- jscript9diag.dll
ms.assetid: a2cb4233-2846-4d11-aa13-21de43abda9f
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2b0a4d595a11dc54829c467a0aace9601042fa08
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575089"
---
# <a name="ijsdebugprocesscreatebreakpoint-method"></a>IJsDebugProcess::CreateBreakPoint メソッド
指定されたドキュメントの位置にブレークポイントを設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CreateBreakPoint(  
   UINT64 documentId,  
   DWORD characterOffset,  
   DWORD characterCount,  
   BOOL isEnabled,  
   IJsDebugBreakPoint **ppDebugBreakPoint  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `documentId`  
 [入力] IDebugDocumentText へのポインター。  
  
 `characterOffset`  
 [入力] ファイルの先頭からの文字オフセット。  
  
 `characterCount`  
 [入力] ブレークポイントを挿入するドキュメント テキストの長さ。  
  
 `isEnabled`  
 [入力] ブレークポイントが有効かどうかを指定します。  
  
 `ppDebugBreakPoint`  
 [出力] 作成されたブレークポイントを表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="requirements"></a>［要件］  
 **ヘッダー:** jscript9diag.h  
  
## <a name="see-also"></a>関連項目  
 [IJsDebugProcess インターフェイス](../../winscript/reference/ijsdebugprocess-interface.md)