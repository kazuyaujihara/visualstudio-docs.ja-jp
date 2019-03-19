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
ms.openlocfilehash: 99fa06086bfad56b266b043716e82181aa4c97d5
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58160629"
---
# <a name="iactivescriptparseprocedureold-interface"></a>IActiveScriptParseProcedureOld インターフェイス
スクリプトに追加する手順については、ソース コードのテキストを使用できます。 これにより、解釈されたスクリプト言語 VBScript などの独立系のオーサリング環境がないための代替手段 (以外の`IActiveScriptParse`または`IPersist*`) 名前空間にスクリプトの手順を追加します。  
  
> [!NOTE]
>  このインターフェイスが好評だったの非推奨とされます、`IActiveScriptParseProcedure`インターフェイス。  
  
## <a name="methods"></a>メソッド  
 継承されたメソッドだけでなく`IUnknown`、`IActiveScriptParseProcedureOld`インターフェイスは、次のメソッドを公開します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptParseProcedureOld::ParseProcedureText](../../winscript/reference/iactivescriptparseprocedureold-parseproceduretext.md)|指定したコードのプロシージャを解析し、名前空間、プロシージャを追加します。|  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptParseProcedure](../../winscript/reference/iactivescriptparseprocedure.md)