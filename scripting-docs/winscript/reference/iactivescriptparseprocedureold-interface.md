---
title: IActiveScriptParseProcedureOld インターフェイス |Microsoft Docs
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
ms.openlocfilehash: 520d3f1414447abfc7c018d36853b72aefbbf15f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63386165"
---
# <a name="iactivescriptparseprocedureold-interface"></a>IActiveScriptParseProcedureOld インターフェイス
スクリプトに追加する手順については、ソース コードのテキストを使用できます。 これにより、解釈されたスクリプト言語 VBScript などの独立系のオーサリング環境がないための代替手段 (以外の`IActiveScriptParse`または`IPersist*`) 名前空間にスクリプトの手順を追加します。  
  
> [!NOTE]
> このインターフェイスが好評だったの非推奨とされます、`IActiveScriptParseProcedure`インターフェイス。  
  
## <a name="methods"></a>メソッド  
 継承されたメソッドだけでなく`IUnknown`、`IActiveScriptParseProcedureOld`インターフェイスは、次のメソッドを公開します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptParseProcedureOld::ParseProcedureText](../../winscript/reference/iactivescriptparseprocedureold-parseproceduretext.md)|指定したコードのプロシージャを解析し、名前空間、プロシージャを追加します。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptParseProcedure](../../winscript/reference/iactivescriptparseprocedure.md)