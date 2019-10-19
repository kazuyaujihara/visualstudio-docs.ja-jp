---
title: 'IActiveScript:: AddNamedItem |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.AddNamedItem
apilocation:
- scrobj.dll
helpviewer_keywords:
- AddNamedItem method, IActiveScript interface
ms.assetid: a7c6317d-948f-4bb3-b169-1bbe5b7c7cc5
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a343e38b944ca36da221da39832046c19b332230
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575819"
---
# <a name="iactivescriptaddnameditem"></a>IActiveScript::AddNamedItem
ルートレベルの項目の名前をスクリプトエンジンの名前空間に追加します。 ルートレベルの項目は、プロパティとメソッド、イベントソース、または3つすべてを含むオブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT AddNamedItem(  
    LPCOLESTR pstrName,  // address of item name  
    DWORD dwFlags          // item flags  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pstrName`  
 からスクリプトから表示される項目の名前を格納しているバッファーのアドレス。 名前は一意であり、持続可能でなければなりません。  
  
 `dwFlags`  
 から項目に関連付けられているフラグ。 次の値の組み合わせが可能です。  
  
|[値]|説明|  
|-----------|-------------|  
|SCRIPTITEM_CODEONLY|名前付き項目がコードのみのオブジェクトを表し、このコードのみのオブジェクトに関連付けられている `IUnknown` がホストにないことを示します。 ホストには、このオブジェクトの名前のみがあります。 などのオブジェクト指向言語ではC++、このフラグによってクラスが作成されます。 すべての言語でこのフラグがサポートされるわけではありません。|  
|SCRIPTITEM_GLOBALMEMBERS|項目が、スクリプトに関連付けられているグローバルプロパティとメソッドのコレクションであることを示します。 通常、スクリプトエンジンでは、オブジェクト名 ( [IActiveScriptSite:: GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md)メソッドのクッキーとして使用する目的、または明示的なスコープを解決するためのもの) を無視し、そのメンバーをグローバル変数およびメソッドとして公開します。 これにより、ホストは、スクリプトで使用できるライブラリ (ランタイム関数など) を拡張できます。 名前の競合を処理するためにスクリプトエンジンが残されています (たとえば、2つの SCRIPTITEM_GLOBALMEMBERS items に同じ名前のメソッドがある場合)。ただし、このような状況によってエラーが返されることはありません。|  
|SCRIPTITEM_ISPERSISTENT|スクリプトエンジンが保存されている場合に、アイテムを保存することを示します。 同様に、このフラグを設定すると、初期化された状態への遷移が、項目の名前と型情報を保持する必要があることを示します (ただし、スクリプトエンジンは、実際のオブジェクトのインターフェイスへのすべてのポインターを解放する必要があります)。|  
|SCRIPTITEM_ISSOURCE|は、スクリプトがシンクできるイベントをソースとして使用することを示します。 子オブジェクト (それ自体がオブジェクトに含まれるオブジェクトのプロパティ) は、スクリプトにイベントを送信することもできます。 これは再帰的ではありませんが、一般的なケースに便利なメカニズムを提供します。たとえば、コンテナーとそのすべてのメンバーコントロールを作成します。|  
|SCRIPTITEM_ISVISIBLE|項目の名前がスクリプトの名前空間で使用できることを示します。これにより、項目のプロパティ、メソッド、およびイベントへのアクセスが許可されます。 慣例として、項目のプロパティには項目の子が含まれます。そのため、すべての子オブジェクトのプロパティとメソッド (およびそれらの子を再帰的に) にアクセスできます。|  
|SCRIPTITEM_NOCODE|項目が単にスクリプトの名前空間に追加される名前であり、コードを関連付ける必要がある項目として処理しないことを示します。 たとえば、このフラグが設定されていない場合、VBScript は名前付き項目に対してC++個別のモジュールを作成し、名前付き項目に対して個別のラッパークラスを作成することがあります。|  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_INVALIDARG`|引数が無効です。|  
|`E_POINTER`|無効なポインターが指定されました。|  
|`E_UNEXPECTED`|この呼び出しは想定されていませんでした (たとえば、スクリプトエンジンがまだ読み込まれていないか、初期化されていません)。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)