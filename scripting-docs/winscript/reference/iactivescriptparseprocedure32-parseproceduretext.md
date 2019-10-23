---
title: IActiveScriptParseProcedure32::P arseProcedureText |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede37171-2f1e-4467-a358-17bd4a4f1869
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: 713421a43d24d8ed7060b3ec4dfbf0f1c42e6249
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574881"
---
# <a name="iactivescriptparseprocedure32parseproceduretext"></a>IActiveScriptParseProcedure32::P arseProcedureText
指定されたコードプロシージャを解析し、名前空間にプロシージャを追加します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT ParseProcedureText(  
    LPCOLESTR pstrCode,              // address of procedure text  
    LPCOLESTR pstrFormalParams,      // address of formal parameter names  
    LPCOLESTR pstrProcedureName,     // address of procedure name  
    LPCOLESTR pstrItemName,          // address of item name  
    IUnknown *punkContext,           // address of debugging context  
    LPCOLESTR pstrDelimiter,         // address of end-of-procedure delimiter  
    DWORD_PTR dwSourceContextCookie, // application-defined value for debugging  
    ULONG ulStartingLineNumber,      // starting line of the script  
    DWORD dwFlags,                   // procedure flags  
    IDispatch **ppdisp               // receives IDispatch pointer  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pstrCode`  
 から評価するプロシージャテキストのアドレス。 この文字列の解釈はスクリプト言語によって異なります。  
  
 `pstrFormalParams`  
 からプロシージャの仮パラメーター名のアドレス。 パラメーター名は、スクリプトエンジンの適切な区切り記号で区切る必要があります。 名前をかっこで囲むことはできません。  
  
 `pstrProcedureName`  
 から解析するプロシージャ名のアドレス。  
  
 `pstrItemName`  
 からプロシージャを評価するコンテキストを指定する項目の名前のアドレス。 このパラメーターが `NULL` 場合、コードはスクリプトエンジンのグローバルコンテキストで評価されます。  
  
 `punkContext`  
 [入力] コンテキスト オブジェクトのアドレス。 このオブジェクトはデバッグ環境用に予約されています。アクティブなランタイム コンテキストを表すためにデバッガーによって指定される場合があります。 このパラメーターが `NULL` 場合、エンジンは `pstrItemName` を使用してコンテキストを識別します。  
  
 `pstrDelimiter`  
 からプロシージャの末尾の区切り記号のアドレス。 テキストのストリームから `pstrCode` を解析する場合、ホストは通常、2つの単一引用符 (' ') などの区切り記号を使用して、プロシージャの終了を検出します。 このパラメーターには、ホストが使用する区切り文字を指定します。それにより、スクリプト エンジンで何らかの条件付きのプリミティブな前処理が可能になります (単一引用符 (') を区切り文字として使用するために 2 つの単一引用符に置き換えるなど)。 スクリプト エンジンがこの情報を厳密にどのような方法 (条件) で使用するかは、スクリプト エンジンによって異なります。 ホストが区切り記号を使用してプロシージャの終了をマークしなかった場合は、このパラメーターを `NULL` に設定します。  
  
 `dwSourceContextCookie`  
 からデバッグの目的で使用されるアプリケーション定義の値。  
  
 `ulStartingLineNumber`  
 [入力] 解析が開始される行を指定するゼロから始まる値。  
  
 `dwFlags`  
 からプロシージャに関連付けられているフラグ。 次の値の組み合わせが可能です。  
  
|[値]|説明|  
|-----------|-------------|  
|SCRIPTPROC_ISEXPRESSION|@No__t_0 内のコードが、プロシージャの戻り値を表す式であることを示します。 既定では、スクリプト言語によってプロシージャで許可されている式、ステートメントのリスト、またはその他の任意のものをコードに含めることができます。|  
|SCRIPTPROC_IMPLICIT_THIS|@No__t_0 ポインターがプロシージャのスコープに含まれることを示します。|  
|SCRIPTPROC_IMPLICIT_PARENTS|@No__t_0 ポインターの親がプロシージャのスコープに含まれることを示します。|  
  
 `ppdisp`  
 入出力スクリプトのグローバルメソッドとプロパティを格納しているオブジェクトのポインターのアドレス。 スクリプトエンジンがこのようなオブジェクトをサポートしていない場合は `NULL` が返されます。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_INVALIDARG`|引数が無効です。|  
|`E_POINTER`|無効なポインターが指定されました。|  
|`E_NOTIMPL`|このメソッドはサポートされていません。 スクリプトエンジンでは、名前空間に対するプロシージャの実行時追加はサポートされていません。|  
|`E_UNEXPECTED`|呼び出しは想定されていませんでした (たとえば、スクリプトエンジンが初期化されていない状態か、閉じられた状態です)。|  
|`OLESCRIPT_E_SYNTAX`|プロシージャで、指定されていない構文エラーが発生しました。|  
|`S_FALSE`|スクリプトエンジンはディスパッチオブジェクトをサポートしていません。`ppdisp` パラメーターが `NULL` に設定されています。|  
  
## <a name="remarks"></a>Remarks  
 この呼び出し中に評価されるスクリプトコードはありません。代わりに、スクリプトによって後で呼び出すことができるスクリプトの状態にプロシージャがコンパイルされます。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptParseProcedure32](../../winscript/reference/iactivescriptparseprocedure32.md)