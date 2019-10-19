---
title: IActiveScriptError |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptError interface
ms.assetid: c8e0288d-38ff-4145-a7e3-f8cdfb72eefe
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ca4d3fe5ff90fc0d116814771308fa599052dba9
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576895"
---
# <a name="iactivescripterror"></a>IActiveScriptError
このインターフェイスを実装するオブジェクトは、スクリプトエンジンによって未処理のエラーが検出されるたびに、 [IActiveScriptSite:: OnScriptError](../../winscript/reference/iactivescriptsite-onscripterror.md)メソッドに渡されます。 次に、ホストはこのオブジェクトのメソッドを呼び出して、発生したエラーに関する情報を取得します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptError::GetExceptionInfo](../../winscript/reference/iactivescripterror-getexceptioninfo.md)|エラーに関する情報を取得します。|  
|[IActiveScriptError::GetSourcePosition](../../winscript/reference/iactivescripterror-getsourceposition.md)|エラーが発生したソースコード内の場所を取得します。|  
|[IActiveScriptError::GetSourceLineText](../../winscript/reference/iactivescripterror-getsourcelinetext.md)|エラーが発生したソースファイル内の行を取得します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト インターフェイス](../../winscript/reference/active-script-interfaces.md)