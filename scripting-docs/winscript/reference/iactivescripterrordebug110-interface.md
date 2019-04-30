---
title: IActiveScriptErrorDebug110 インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptErrorDebug110 Interface
ms.assetid: 5c1a4993-4cad-4ccf-89c2-53abfddfe1f2
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 72f545f5a48fc7b8aa3f9250b13a62ba659e94bc
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63436053"
---
# <a name="iactivescripterrordebug110-interface"></a>IActiveScriptErrorDebug110 インターフェイス
機能を追加、 [IActiveScriptDebug インターフェイス](../../winscript/reference/iactivescriptdebug-interface.md)します。 このインターフェイスは、BREAKREASON_ERROR イベントが発生した理由を確認するために JavaScript エンジンによって実装されます。  
  
> [!IMPORTANT]
> このインターフェイスは、PDM v11.0 以降によって実装されます。 activdbg100.h にあります。  
  
## <a name="methods"></a>メソッド  
 `IActiveScriptErrorDebug110` インターフェイスは、以下のメソッドを公開します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptErrorDebug110::GetExceptionThrownKind](../../winscript/reference/iactivescripterrordebug110-getexceptionthrownkind.md)|スローされた例外の種類を返します。|