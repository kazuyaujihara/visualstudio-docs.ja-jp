---
title: 'IActiveScript:: AddTypeLib |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.AddTypeLib
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_AddTypeLib
ms.assetid: 8e507ea8-c80a-471c-b482-ae753c6e8595
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 254a5133d42689020eaaae290a1016de4b848100
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575809"
---
# <a name="iactivescriptaddtypelib"></a>IActiveScript::AddTypeLib
スクリプトの名前空間にタイプライブラリを追加します。 これは、C/C++の `#include` ディレクティブに似ています。 これにより、定義済みの一連の項目 (クラス定義、`typedefs`、名前付き定数など) をスクリプトで使用できる実行時環境に追加できます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT AddTypeLib(  
    REFGUID guidTypeLib,  // CLSID of type library  
    DWORD dwMaj,          // major version number  
    DWORD dwMin,          // minor version number  
    DWORD dwFlags         // option flags  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `guidTypeLib`  
 から追加するタイプライブラリの CLSID。  
  
 `dwMaj`  
 からメジャーバージョン番号。  
  
 `dwMin`  
 からマイナーバージョン番号。  
  
 `dwFlags`  
 からオプションフラグ。 次のように指定できます。  
  
|[値]|説明|  
|-----------|-------------|  
|SCRIPTTYPELIB_ISCONTROL|タイプライブラリは、ホストによって使用される ActiveX コントロールを記述します。|  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_INVALIDARG`|引数が無効です。|  
|`E_UNEXPECTED`|この呼び出しは想定されていませんでした (たとえば、スクリプトエンジンがまだ読み込まれていないか、初期化されていません)。|  
|`TYPE_E_CANTLOADLIBRARY`|指定されたタイプライブラリを読み込めませんでした。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)