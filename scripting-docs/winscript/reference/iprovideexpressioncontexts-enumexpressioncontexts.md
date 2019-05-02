---
title: IProvideExpressionContexts::EnumExpressionContexts |Microsoft Docs
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
ms.openlocfilehash: 965147083bdc11a3544561fdd96cd85221ccd443
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63410146"
---
# <a name="iprovideexpressioncontextsenumexpressioncontexts"></a>IProvideExpressionContexts::EnumExpressionContexts
このコンポーネントによって認識されている式コンテキストの列挙子を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT EnumExpressionContexts(  
   IEnumDebugExpressionContexts**  ppedec  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppedec`  
 [out]このコンポーネントによって認識されている式コンテキストの列挙子。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは `HRESULT` を返します。 有効な値を次の表に示しますが、これ以外にもあります。  
  
|[値]|説明|  
|-----------|-----------------|  
|`S_OK`|メソッドが成功しました。|  
  
## <a name="remarks"></a>Remarks  
 プロセス デバッグ マネージャーでは、このメソッドを使用して、特定のスレッドに関連付けられているすべてのグローバル式のコンテキストを検索します。  
  
> [!NOTE]
> このメソッドは、関心のあるスレッド内からを呼び出されます。 現在のスレッドを識別して適切な列挙子を返すために、実装者の責任です。  
  
## <a name="see-also"></a>関連項目  
 [IProvideExpressionContexts インターフェイス](../../winscript/reference/iprovideexpressioncontexts-interface.md)