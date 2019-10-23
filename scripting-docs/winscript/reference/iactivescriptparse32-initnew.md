---
title: 'IActiveScriptParse32:: InitNew |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c77aa16-f391-4c93-9f1a-4e529a9930b2
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: 8b5304d60aed8145e7a68d89b2c6d4386db0d745
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72561662"
---
# <a name="iactivescriptparse32initnew"></a>IActiveScriptParse32:: InitNew
スクリプトエンジンを初期化します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT InitNew(void);  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合は `S_OK` を返し、初期化中にエラーが発生した場合は `E_FAIL` します。  
  
## <a name="remarks"></a>Remarks  
 スクリプトエンジンを使用する前に、次のいずれかのメソッドを呼び出す必要があります: `IPersist*::Load`、`IPersist*::InitNew`、または `IActiveScriptParse32::InitNew`。 このメソッドのセマンティクスは `IPersistStreamInit::InitNew` と同じです。このメソッドは、スクリプトエンジンがそれ自体を初期化するように指示します。 @No__t_0 または `IActiveScriptParse32::InitNew` と `IPersist*::Load` の両方を呼び出すことはできません。また、`IPersist*::InitNew`、`IActiveScriptParse32::InitNew`、または `IPersist*::Load` を複数回呼び出すこともできません。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptParse32](../../winscript/reference/iactivescriptparse32.md)