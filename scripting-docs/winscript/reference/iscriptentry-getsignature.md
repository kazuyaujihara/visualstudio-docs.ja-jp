---
title: 'IScriptEntry:: GetSignature |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.GetSignature
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::GetSignature
ms.assetid: 8cbf37ac-b14c-4e15-a613-06f34857da9b
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e7b07ac64ce7e427a793f0af0db9a7905441d39b
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575416"
---
# <a name="iscriptentrygetsignature"></a>IScriptEntry::GetSignature
@No__t_0 関数オブジェクトの型情報を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetSignature(  
   ITypeInfo          **ppti  
   ULONG              *piMethod  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppti`  
 入出力この `IScriptEntry` 関数オブジェクトに関連付けられている型情報。  
  
 `piMethod`  
 入出力@No__t_0 オブジェクトのメソッドインデックス。  
  
## <a name="return-value"></a>戻り値  
 `HRESULT`。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 型情報は、 [Iscriptentry:: SetSignature](../../winscript/reference/iscriptentry-setsignature.md)または[Iscriptentry:: CreateChildHandler](../../winscript/reference/iscriptnode-createchildhandler.md)を使用して設定します。 型情報は、内部関数表現に基づいてエントリによって生成されることもあります。  
  
## <a name="see-also"></a>関連項目  
 [IScriptEntry インターフェイス](../../winscript/reference/iscriptentry-interface.md)