---
title: 'IJsDebugFrame:: Evaluate メソッド |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugFrame.Evaluate
apilocation:
- jscript9diag.dll
ms.assetid: 0ee61340-37b8-4fbb-a028-748b5315e279
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6227b97c1fd5fae32db3e13ef72751726c36b043
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573498"
---
# <a name="ijsdebugframeevaluate-method"></a>IJsDebugFrame::Evaluate メソッド
このスタック フレームのコンテキストで式を評価します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Evaluate(  
   LPCOLESTR pExpressionText,  
   IJsDebugProperty **ppDebugProperty,  
   BSTR *pError  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pExpressionText`  
 [入力] 評価する式。  
  
 `ppDebugProperty`  
 [出力] プロパティ ブラウザーを表すオブジェクト。  
  
 `pError`  
 [出力] エラーが発生した場合のエラーメッセージ。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="remarks"></a>Remarks  
 次のメッセージを返します。"S_OK: Evaluation succeeds, *ppDebugProperty contains evaluation result." S_FALSE: 評価はエラーをスローします (または評価操作はサポートされていません)。 \*pError にはエラーメッセージが含まれています。  
  
## <a name="requirements"></a>［要件］  
 **ヘッダー:** jscript9diag.h  
  
## <a name="see-also"></a>関連項目  
 [IJsDebugFrame インターフェイス](../../winscript/reference/ijsdebugframe-interface.md)