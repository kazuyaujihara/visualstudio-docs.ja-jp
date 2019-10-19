---
title: 'IVariantChangeType:: ChangeType |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IVariantChangeType.ChangeType
apilocation:
- scrobj.dll
helpviewer_keywords:
- IVariantChangeType::ChangeType
ms.assetid: 52374764-c42e-49af-a219-ee00c535a118
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 406d5d8486b3016f0105b7bd8bf231db0e1e9613
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571784"
---
# <a name="ivariantchangetypechangetype"></a>IVariantChangeType::ChangeType
バリアント値を受け取り、指定された型を使用して新しいバリアントを作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT ChangeType(  
   VARIANT*  pvarDst,  
   VARIANT*  pvarSrc,  
   LCID  lcid,  
   VARTYPE  vtNew  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pvarDst`  
 [入力、出力]@No__t_1 によって指定された型を使用して、`pvarSrc` によって表される値を格納するバリアント。  
  
 `pvarSrc`  
 から新しい型に変更するバリアント値。  
  
 `lcid`  
 から引数を文字列との間で変換するときに使用するロケールコンテキスト。  
  
 `vtNew`  
 から@No__t_0 の種類を指定します。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 @No__t_0 引数と `pvarSrc` 引数が等しい場合は、元の値が上書きされます。 このメソッドは `pvarDst` を `VariantClear` 関数に渡し、その結果 `pvarDst` を有効な値に初期化する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [IVariantChangeType インターフェイス](../../winscript/reference/ivariantchangetype-interface.md)