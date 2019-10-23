---
title: 'IDispError:: GetHelpInfo |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispError.GetHelpInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDispError::GetHelpInfo
ms.assetid: a146df13-eda4-4e56-8bf0-cf9886a2150f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a84e57e97bb781ad3ea0be1ac6766fd94f6f5c30
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573133"
---
# <a name="idisperrorgethelpinfo"></a>IDispError::GetHelpInfo
可能な場合は、ヘルプファイルのパスと、エラーを説明するトピックのコンテキスト ID を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetHelpInfo(  
   BSTR*  pbstrFileName,  
   DWORD*  pdwContext  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstrFileName`  
 入出力ヘルプファイルの完全修飾パスを含む文字列。 ヘルプファイルがない場合、またはエラーが発生した場合、戻り値は NULL になります。  
  
 `pdwContext`  
 入出力エラーのヘルプコンテキスト ID。 ヘルプファイルがない場合 (`pbstrFileName` が NULL の場合)、このパラメーターには意味がありません。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
|`E_FAIL`|プロバイダー固有のエラーが発生しました。|  
|`E_INVALIDARG`|`pbstrFileName` または `pdwContext` が NULL でした。|  
|`E_OUTOFMEMORY`|プロバイダーは、ヘルプファイルのパスを返すのに十分なメモリを割り当てることができませんでした。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、可能であれば、ヘルプファイルのパスと、エラーを説明するトピックのコンテキスト ID を返します。  
  
> [!NOTE]
> このメソッドは実装されていません。  
  
## <a name="see-also"></a>関連項目  
 [IDispError インターフェイス](../../winscript/reference/idisperror-interface.md)