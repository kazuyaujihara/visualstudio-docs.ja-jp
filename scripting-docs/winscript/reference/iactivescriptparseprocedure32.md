---
title: IActiveScriptParseProcedure32 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 387a856b-f5dc-4371-8620-bd574e046c2c
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: 1993cbef966a4d73a2a3ed55c3317db444702232
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574875"
---
# <a name="iactivescriptparseprocedure32"></a>IActiveScriptParseProcedure32
Windows スクリプトエンジンで、プロシージャのソースコードテキストをスクリプトに追加することが許可されている場合は、`IActiveScriptParseProcedure32` インターフェイスが実装されます。 VBScript など、独立した作成環境を持たない解釈されたスクリプト言語では、スクリプトプロシージャを名前空間に追加するための代替メカニズム (`IActiveScriptParse32` または `IPersist` * 以外) が提供されます。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|||  
|-|-|  
|メソッド|説明|  
|[IActiveScriptParseProcedure32::ParseProcedureText](../../winscript/reference/iactivescriptparseprocedure32-parseproceduretext.md)|指定されたコードプロシージャを解析し、プロシージャを名前空間に追加します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト インターフェイス](../../winscript/reference/active-script-interfaces.md)