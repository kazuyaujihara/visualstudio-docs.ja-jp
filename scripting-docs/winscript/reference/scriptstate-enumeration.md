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
ms.openlocfilehash: fe6a05c5e73d26a8daa9e46c317422d85d1c40be
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62840162"
---
# <a name="scriptstate-enumeration"></a>SCRIPTSTATE 列挙型
スクリプト エンジンの状態を指定します。 この列挙体を使って、 [IActiveScript::GetScriptState](../../winscript/reference/iactivescript-getscriptstate.md) 、 [iactivescript::setscriptstate](../../winscript/reference/iactivescript-setscriptstate.md) 、および[IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md)メソッド。  
  
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
|SCRIPTSTATE_UNINITIALIZED|スクリプトが作成された直後がまだ初期化されていないを使用して、`IPersist*`インターフェイスと[iactivescript::setscriptsite](../../winscript/reference/iactivescript-setscriptsite.md)します。|  
|SCRIPTSTATE_INITIALIZED|スクリプトが初期化されてはいない (他のオブジェクトへの接続またはシンク イベント) を実行しているをコードを実行します。 コードを呼び出すことによって実行を照会することができます、 [iactivescriptparse::parsescripttext](../../winscript/reference/iactivescriptparse-parsescripttext.md)メソッド。|  
|SCRIPTSTATE_STARTED|コードを実行できるスクリプトによって追加されたオブジェクトのイベントをシンクはありませんが、 [iactivescript::addnameditem](../../winscript/reference/iactivescript-addnameditem.md)メソッド。|  
|SCRIPTSTATE_CONNECTED|スクリプトが読み込まれ、イベントをシンクに接続されています。|  
|SCRIPTSTATE_DISCONNECTED|スクリプトが読み込まれるとランタイム実行の状態が、シンク イベントから一時的に切断されています。|  
|SCRIPTSTATE_CLOSED|スクリプトが閉じられました。 スクリプト エンジンは動作しなくなり、ほとんどのメソッドに対してエラーを返します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプトの定数、列挙型、およびエラー コード](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)