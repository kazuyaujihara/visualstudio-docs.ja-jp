---
title: IActiveScriptParseProcedureOld Interface |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptParseProcedureOld
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptParseProcedureOld interface
ms.assetid: d94b391e-4c24-46da-a01f-2c134ca4f041
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4558a0cab2aea9b56db2759bb80b1287cd33ce87
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72571424"
---
# <a name="iactivescriptparseprocedureold-interface"></a>IActiveScriptParseProcedureOld インターフェイス
プロシージャのソースコードテキストをスクリプトに追加できるようにします。 VBScript などの独立した作成環境がない解釈されたスクリプト言語では、スクリプトプロシージャを名前空間に追加するための代替メカニズム (`IActiveScriptParse` または `IPersist*` 以外) が提供されます。  
  
> [!NOTE]
> このインターフェイスは、`IActiveScriptParseProcedure` インターフェイスを優先して非推奨とされます。  
  
## <a name="methods"></a>メソッド  
 @No__t_1 インターフェイスは、`IUnknown` から継承されたメソッドに加えて、次のメソッドを公開します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptParseProcedureOld::ParseProcedureText](../../winscript/reference/iactivescriptparseprocedureold-parseproceduretext.md)|指定されたコードプロシージャを解析し、名前空間にプロシージャを追加します。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptParseProcedure](../../winscript/reference/iactivescriptparseprocedure.md)