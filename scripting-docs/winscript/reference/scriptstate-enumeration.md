---
title: SCRIPTSTATE 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- SCRIPTSTATE
apilocation:
- scrobj.dll
helpviewer_keywords:
- SCRIPTSTATE enum
ms.assetid: 5f5deb05-c4bb-4964-8077-e624c6b2a14e
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 10dd6366e2d0783ec2e9d6bdadc001e9f999901e
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575677"
---
# <a name="scriptstate-enumeration"></a>SCRIPTSTATE 列挙型
スクリプトエンジンの状態を指定します。 この列挙体は、 [IActiveScript:: GetScriptState](../../winscript/reference/iactivescript-getscriptstate.md) 、 [IActiveScript:: setscriptstate](../../winscript/reference/iactivescript-setscriptstate.md) 、および[IActiveScriptSite:: OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md)メソッドによって使用されます。  
  
## <a name="syntax"></a>構文  
  
```cpp
typedef enum tagSCRIPTSTATE {  
    SCRIPTSTATE_UNINITIALIZED = 0,  
    SCRIPTSTATE_INITIALIZED   = 5,  
    SCRIPTSTATE_STARTED       = 1,  
    SCRIPTSTATE_CONNECTED     = 2,  
    SCRIPTSTATE_DISCONNECTED  = 3,  
    SCRIPTSTATE_CLOSED        = 4  
} SCRIPTSTATE;  
```  
  
## <a name="enumeration-values"></a>列挙値  
  
|||  
|-|-|  
|SCRIPTSTATE_UNINITIALIZED|スクリプトは作成されたばかりですが、`IPersist*` インターフェイスと[IActiveScript:: SetScriptSite](../../winscript/reference/iactivescript-setscriptsite.md)を使用してまだ初期化されていません。|  
|SCRIPTSTATE_INITIALIZED|スクリプトは初期化されていますが、実行されていない (他のオブジェクトまたはシンクイベントに接続している) か、任意のコードを実行しています。 [IActiveScriptParse::P arsescripttext](../../winscript/reference/iactivescriptparse-parsescripttext.md)メソッドを呼び出すことにより、コードの実行をクエリできます。|  
|SCRIPTSTATE_STARTED|スクリプトでコードを実行できますが、 [IActiveScript:: AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md)メソッドによって追加されたオブジェクトのイベントはまだシンクされていません。|  
|SCRIPTSTATE_CONNECTED|スクリプトが読み込まれ、シンクイベント用に接続されています。|  
|SCRIPTSTATE_DISCONNECTED|スクリプトが読み込まれ、実行時の実行状態になっていますが、シンクイベントから一時的に切断されています。|  
|SCRIPTSTATE_CLOSED|スクリプトは閉じられました。 スクリプト エンジンは動作しなくなり、ほとんどのメソッドに対してエラーを返します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプトの定数、列挙型、およびエラー コード](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)