---
title: 'Iの式のコンテキスト:: Enum式のコンテキスト |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IProvideExpressionContexts.EnumExpressionContexts
apilocation:
- jscript.dll
helpviewer_keywords:
- IProvideExpressionContexts::EnumExpressionContexts
ms.assetid: ec5f0065-00df-41e6-b480-4c04ba464872
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f161c1591267af1398d5c04d00623381cfae2ad4
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572390"
---
# <a name="iprovideexpressioncontextsenumexpressioncontexts"></a>IProvideExpressionContexts::EnumExpressionContexts
このコンポーネントによって認識される式コンテキストの列挙子を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT EnumExpressionContexts(  
   IEnumDebugExpressionContexts**  ppedec  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppedec`  
 入出力このコンポーネントによって認識される式コンテキストの列挙子。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 プロセスデバッグマネージャーは、このメソッドを使用して、特定のスレッドに関連付けられているすべてのグローバル式コンテキストを検索します。  
  
> [!NOTE]
> このメソッドは、対象のスレッド内から呼び出されます。 現在のスレッドを識別し、適切な列挙子を返すのは、実装者の作業です。  
  
## <a name="see-also"></a>関連項目  
 [IProvideExpressionContexts インターフェイス](../../winscript/reference/iprovideexpressioncontexts-interface.md)