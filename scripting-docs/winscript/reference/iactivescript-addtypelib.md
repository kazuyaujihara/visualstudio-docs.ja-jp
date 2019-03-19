---
title: IActiveScript::AddTypeLib |Microsoft Docs
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
ms.openlocfilehash: c4943d1305c2f25de4eec9e782949a66827de879
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144876"
---
# <a name="iactivescriptaddtypelib"></a>IActiveScript::AddTypeLib
スクリプトの名前空間には、タイプ ライブラリを追加します。 これに似ています、 `#include` C と C++ のディレクティブ。 これにより、クラスの定義などの定義済みの項目のセットを`typedefs`、名前付き定数、スクリプトで使用できるランタイム環境に追加するとします。  
  
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
 [in]追加するタイプ ライブラリの CLSID。  
  
 `dwMaj`  
 [in]メジャー バージョン番号。  
  
 `dwMin`  
 [in]マイナー バージョン番号。  
  
 `dwFlags`  
 [in]オプションのフラグ。 次を指定できます。  
  
|[値]|説明|  
|-----------|-------------|  
|SCRIPTTYPELIB_ISCONTROL|タイプ ライブラリには、ホストによって使用される ActiveX コントロールについて説明します。|  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_INVALIDARG`|引数が無効です。|  
|`E_UNEXPECTED`|呼び出しが予期されていませんでした (たとえば、スクリプト エンジンがされていないされて読み込まれるまたは初期化) します。|  
|`TYPE_E_CANTLOADLIBRARY`|指定したタイプ ライブラリを読み込むことができませんでした。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)