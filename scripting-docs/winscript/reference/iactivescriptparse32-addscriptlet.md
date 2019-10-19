---
title: 'IActiveScriptParse32:: AddScriptlet レット |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fcf11eb2-8e71-4cca-afda-a91791c243ff
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: b48d89ce2c49bd971fe298d2b4773aad8b65e8c3
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72561695"
---
# <a name="iactivescriptparse32addscriptlet"></a>IActiveScriptParse32:: AddScriptlet レット
スクリプトにコードレットを追加します。 このメソッドは、スクリプトの永続的な状態がホストドキュメントと関係ていて、ホストが `IPersist*` インターフェイスではなく、スクリプトの復元を担当する環境で使用されます。 主な例は、html ドキュメントに埋め込まれているコードのスクリプトレットを組み込みイベントに添付できるようにする HTML スクリプト言語 (たとえば、ONCLICK = "button1. text = ' Exit '") です。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT AddScriptlet(  
    LPCOLESTR pstrDefaultName,       // address of default name of scriptlet  
    LPCOLESTR pstrCode,              // address of scriptlet text  
    LPCOLESTR pstrItemName,          // address of item name  
    LPCOLESTR pstrSubItemName,       // address of subitem name  
    LPCOLESTR pstrEventName,         // address of event name  
    LPCOLESTR pstrDelimiter,         // address of end-of-scriptlet delimiter  
    DWORD_PTR dwSourceContextCookie, // application-defined value for debugging  
    ULONG ulStartingLineNumber,      // starting line of the script  
    DWORD dwFlags,                   // scriptlet flags  
    BSTR *pbstrName,                 // address of actual name of scriptlet  
    EXCEPINFO *pexcepinfo            // address of exception information  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pstrDefaultName`  
 からスクリプトレットに関連付ける既定の名前のアドレス。 前の例のように、スクリプトレットに名前付け情報が含まれていない場合は、この名前を使用してスクリプトレットが識別されます。 このパラメーターが `NULL` 場合は、必要に応じて、スクリプトエンジンによって一意の名前が作成されます。  
  
 `pstrCode`  
 から追加するスクリプトレットテキストのアドレス。 この文字列の解釈はスクリプト言語によって異なります。  
  
 `pstrItemName`  
 からこのスクリプトレットに関連付けられている項目名を格納しているバッファーのアドレス。 このパラメーターは、`pstrSubItemName` に加えて、スクリプトレットがイベントハンドラーとして使用されるオブジェクトを識別します。  
  
 `pstrSubItemName`  
 からこのスクリプトレットが関連付けられている名前付き項目の `subobject` の名前を格納しているバッファーのアドレス。この名前は、名前付き項目の型情報に含まれている必要があります。 スクリプトレットが `subitem` ではなく名前付き項目に関連付けられている場合、このパラメーターは NULL になります。 このパラメーターは、`pstrItemName` に加えて、スクリプトレットがイベントハンドラーとして使用される特定のオブジェクトを識別します。  
  
 `pstrEventName`  
 からスクリプトレットがイベントハンドラーであるイベントの名前を格納しているバッファーのアドレス。  
  
 `pstrDelimiter`  
 [入力] スクリプトレット末尾の区切り記号のアドレス。 @No__t_0 パラメーターがテキストのストリームから解析される場合、ホストは通常、2つの単一引用符 (' ') などの区切り記号を使用して、スクリプトレットの終了を検出します。 このパラメーターには、ホストが使用する区切り文字を指定します。それにより、スクリプト エンジンで何らかの条件付きのプリミティブな前処理が可能になります (単一引用符 (') を区切り文字として使用するために 2 つの単一引用符に置き換えるなど)。 スクリプト エンジンがこの情報を厳密にどのような方法 (条件) で使用するかは、スクリプト エンジンによって異なります。 ホストがスクリプトレットの末尾を示すために区切り記号を使用しなかった場合は、このパラメーターを NULL に設定します。  
  
 `dwSourceContextCookie`  
 からデバッグの目的で使用されるアプリケーション定義の値。  
  
 `ulStartingLineNumber`  
 [入力] 解析が開始される行を指定するゼロから始まる値。  
  
 `dwFlags`  
 [入力] スクリプトレットに関連付けられるフラグ。 は、次の値の組み合わせにすることができます。  
  
|戻り値|説明|  
|------------------|-------------|  
|SCRIPTTEXT_ISVISIBLE|スクリプト テキストをスクリプトの名前空間内でグローバル メソッドとして参照可能にする (名前で呼び出せるようにする) 必要があることを指定します。|  
|SCRIPTTEXT_ISPERSISTENT|スクリプト エンジンが保存される場合 (`IPersist*::Save` の呼び出しなどにより)、または初期化状態に戻すことでリセットされる場合、この呼び出し中に追加されたコードを保存する必要があることを指定します。 この状態の詳細については、「スクリプトエンジンの状態」を参照してください。|  
  
 `pbstrName` ,  
 入出力スクリプトレットを識別するために使用される実際の名前。 これは、優先順位の順になります。つまり、スクリプトレットテキストに明示的に指定された名前、`pstrDefaultName` で指定された既定の名前、またはスクリプトエンジンによって合成された一意の名前です。  
  
 `pexcepinfo` ,  
 入出力例外情報を格納している構造体のアドレス。 DISP_E_EXCEPTION が返される場合は、この構造体を入力する必要があります。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`DISP_E_EXCEPTION`|スクリプトレットの解析中に例外が発生しました。 `pexcepinfo` パラメーターに例外に関する情報が格納されます。|  
|`E_INVALIDARG`|引数が無効です。|  
|`E_NOTIMPL`|このメソッドはサポートされていません。スクリプトエンジンでは、イベントシンクスクリプトレットの追加はサポートされていません。|  
|`E_POINTER`|無効なポインターが指定されました。|  
|`E_UNEXPECTED`|呼び出しは想定されていませんでした (たとえば、スクリプトエンジンがまだ読み込まれていないか初期化されていないため)。そのため失敗しました。|  
|`OLESCRIPT_E_INVALIDNAME`|指定された既定の名前は、このスクリプト言語では無効です。|  
|`OLESCRIPT_E_SYNTAX`|指定されていない構文エラーがスクリプトレットで発生しました。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptParse32](../../winscript/reference/iactivescriptparse32.md)