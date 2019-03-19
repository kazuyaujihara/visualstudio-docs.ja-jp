---
title: APPBREAKFLAGS 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- APPBREAKFLAGS
apilocation:
- scrobj.dll
helpviewer_keywords:
- APPBREAKFLAGS constants
ms.assetid: ea8ed80f-2ddb-4800-bb3b-52b76ba6c7a0
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0862e6fc670be6cd3d3ca9fbf67f453aa0772a90
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58158985"
---
# <a name="appbreakflags-enumeration"></a>APPBREAKFLAGS 列挙型
アプリケーションおよびスレッドの現在のデバッグ状態を示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum enum_APPBREAKFLAGS{APPBREAKFLAG_DEBUGGER_BLOCK= 0x00000001,APPBREAKFLAG_DEBUGGER_HALT= 0x00000002,APPBREAKFLAG_STEP= 0x00010000,APPBREAKFLAG_NESTED= 0x00020000,APPBREAKFLAG_STEPTYPE_SOURCE= 0x00000000,APPBREAKFLAG_STEPTYPE_BYTECODE= 0x00100000,APPBREAKFLAG_STEPTYPE_MACHINE= 0x00200000,APPBREAKFLAG_STEPTYPE_MASK= 0x00F00000,APPBREAKFLAG_IN_BREAKPOINT= 0x80000000};  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|[値]|説明|  
|------------|-----------|-----------------|  
|APPBREAKFLAG_DEBUGGER_BLOCK|0x00000001|言語エンジンが、BREAKREASON_DEBUGGER_BLOCK ですべてのスレッドですぐに中断する必要があります。|  
|APPBREAKFLAG_DEBUGGER_HALT|0x00000002|言語エンジンは、BREAKREASON_DEBUGGER_HALT ですぐに中断する必要があります。|  
|APPBREAKFLAG_STEP|0x00010000|言語エンジンは、BREAKREASON_STEP でステップ実行のスレッドですぐに中断する必要があります。|  
|APPBREAKFLAG_NESTED|0x00020000|アプリケーションがブレークポイントで実行が入れ子になったです。|  
|APPBREAKFLAG_STEPTYPE_SOURCE|0x00000000|デバッガーは、ソース レベルでステップ実行します。|  
|APPBREAKFLAG_STEPTYPE_BYTECODE|0x00100000|デバッガーはコードのバイト レベルのステップ実行します。|  
|APPBREAKFLAG_STEPTYPE_MACHINE|0x00200000|デバッガーは、コンピューター レベルでステップ実行します。|  
|APPBREAKFLAG_STEPTYPE_MASK|0x00F00000|ステップの種類を取り除くのマスクです。|  
|APPBREAKFLAG_IN_BREAKPOINT|0x80000000|ブレークポイントは、実行中です。|  
  
## <a name="remarks"></a>Remarks  
 一部のフラグは、言語エンジンは、その他のフラグは、デバッガーのステップ実行モードを指定では、次の機会に中断する必要がありますを指定します。  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト デバッガーの定数、列挙型、および構造体](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)   
 [BREAKREASON 列挙型](../../winscript/reference/breakreason-enumeration.md)