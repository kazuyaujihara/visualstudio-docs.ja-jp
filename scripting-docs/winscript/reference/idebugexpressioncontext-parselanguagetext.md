---
title: IDebugExpressionContext::P arseLanguageText |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpressionContext.ParseLanguageText
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpressionContext::ParseLanguageText
ms.assetid: 650cb016-7d80-4011-b264-780f871a3466
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0493adde76e029088b637be3c6aaf02c55caaace
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573152"
---
# <a name="idebugexpressioncontextparselanguagetext"></a>IDebugExpressionContext::ParseLanguageText
指定したテキストのデバッグ式を作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT ParseLanguageText(  
   LPCOLESTR           pstrCode,  
   UINT                nRadix,  
   LPCOLESTR           pstrDelimiter,  
   DWORD               dwFlags,  
   IDebugExpression**  ppe  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pstrCode`  
 から式またはステートメントのテキストを提供します。  
  
 `nRadix`  
 [入力] 使用する基数。  
  
 `pstrDelimiter`  
 からスクリプトの末尾の区切り記号。 テキストのストリームから `pstrCode` を解析する場合、ホストは通常、2つの単一引用符 (' ') などの区切り記号を使用して、スクリプトブロックの終了を検出します。 このパラメーターには、ホストが使用する区切り文字を指定します。それにより、スクリプト エンジンで何らかの条件付きのプリミティブな前処理が可能になります (単一引用符 (') を区切り文字として使用するために 2 つの単一引用符に置き換えるなど)。 スクリプトエンジンがこの情報を使用する方法 (および if) は、スクリプトエンジンによって異なります。 ホストがスクリプトブロックの末尾を示すために区切り記号を使用しなかった場合は、このパラメーターを `NULL` に設定します。  
  
 `dwFlags`  
 から次のデバッグテキストフラグの組み合わせ。  
  
|定数|[値]|説明|  
|--------------|-----------|-----------------|  
|DEBUG_TEXT_ISEXPRESSION|0x00000001|テキストがステートメントではなく式であることを示します。 このフラグは、一部の言語によるテキストの解析方法に影響する場合があります。|  
|DEBUG_TEXT_RETURNVALUE|0x00000002|戻り値が使用できる場合、その値は呼び出し元によって使用されます。|  
|DEBUG_TEXT_NOSIDEEFFECTS|0x00000004|副作用を許可しません。 このフラグが設定されている場合は、ランタイム状態が式の評価によって変更されることはありません。|  
|DEBUG_TEXT_ALLOWBREAKPOINTS|0x00000008|テキストの評価中にブレークポイントを許可します。 このフラグが設定されていない場合、テキストの評価中にブレークポイントは無視されます。|  
|DEBUG_TEXT_ALLOWERRORREPORT|0x00000010|テキストの評価中にエラーレポートを使用できるようにします。 このフラグが設定されていない場合、評価中にエラーはホストに報告されません。|  
|DEBUG_TEXT_EVALUATETOCODECONTEXT|0x00000020|式自体を実行するのではなく、式がコードコンテキストに評価されることを示します。|  
  
 `ppe`  
 入出力指定されたテキストのデバッグ式を返します。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、指定されたテキストに対してデバッグ式を作成します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugExpressionContext インターフェイス](../../winscript/reference/idebugexpressioncontext-interface.md)