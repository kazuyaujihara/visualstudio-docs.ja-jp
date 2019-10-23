---
title: 'IActiveScriptParse:: InitNew |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptParse.InitNew
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptParse_InitNew
ms.assetid: 3a582bd6-fc0d-43a5-812f-5ea55a8517a1
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b4817e103d7408124f35eb7dbaa16e955dd18f17
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573507"
---
# <a name="iactivescriptparseinitnew"></a>IActiveScriptParse::InitNew
スクリプトエンジンを初期化します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT InitNew(void);  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合は `S_OK` を返し、初期化中にエラーが発生した場合は `E_FAIL` します。  
  
## <a name="remarks"></a>Remarks  
 スクリプトエンジンを使用する前に、次のいずれかのメソッドを呼び出す必要があります: `IPersist*::Load`、`IPersist*::InitNew`、または `IActiveScriptParse::InitNew`。 このメソッドのセマンティクスは `IPersistStreamInit::InitNew` と同じです。このメソッドは、スクリプトエンジンがそれ自体を初期化するように指示します。 @No__t_0 または `IActiveScriptParse::InitNew` と `IPersist*::Load` の両方を呼び出すことはできません。また、`IPersist*::InitNew`、`IActiveScriptParse::InitNew`、または `IPersist*::Load` を複数回呼び出すこともできません。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptParse](../../winscript/reference/iactivescriptparse.md)