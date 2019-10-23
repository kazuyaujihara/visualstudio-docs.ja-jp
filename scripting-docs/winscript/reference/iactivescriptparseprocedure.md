---
title: IActiveScriptParseProcedure |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptParseProcedure interface
ms.assetid: 741a35bb-5b92-489e-ba8a-a406b42125fc
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c20947a125766547565d99c5762c20e23652da1a
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72561672"
---
# <a name="iactivescriptparseprocedure"></a>IActiveScriptParseProcedure
Windows スクリプトエンジンで、プロシージャのソースコードテキストをスクリプトに追加することが許可されている場合は、`IActiveScriptParseProcedure` インターフェイスが実装されます。 VBScript など、独立した作成環境を持たない解釈されたスクリプト言語では、スクリプトプロシージャを名前空間に追加するための代替メカニズム (`IActiveScriptParse` または `IPersist` * 以外) が提供されます。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|||  
|-|-|  
|メソッド|説明|  
|[IActiveScriptParseProcedure::ParseProcedureText](../../winscript/reference/iactivescriptparseprocedure-parseproceduretext.md)|指定されたコードプロシージャを解析し、プロシージャを名前空間に追加します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト インターフェイス](../../winscript/reference/active-script-interfaces.md)