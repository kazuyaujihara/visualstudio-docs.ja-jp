---
title: IScriptEntry インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IScriptEntry interface
ms.assetid: 86da3bc1-58b7-4d73-87ab-bc3ce34e3f41
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 868322358908a32c8f14b56846cf3237f8531b4c
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575392"
---
# <a name="iscriptentry-interface"></a>IScriptEntry インターフェイス
@No__t_0 インターフェイスを実装するオブジェクトは、スクリプトブロックまたは関数オブジェクトを表します。  
  
 @No__t_1 インターフェイスは、`IScriptNode` から継承されたメソッドに加えて、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IScriptEntry::GetBody](../../winscript/reference/iscriptentry-getbody.md)|@No__t_0 スクリプトブロック、関数ブロック、またはスクリプトレットの本体に対応するテキストを返します。|  
|[IScriptEntry::GetItemName](../../winscript/reference/iscriptentry-getitemname.md)|@No__t_0 オブジェクトを識別する項目名を返します。|  
|[IScriptEntry::GetName](../../winscript/reference/iscriptentry-getname.md)|1つのオブジェクト (関数など) を表すエントリの場合、はオブジェクトの名前を返します。|  
|[IScriptEntry::GetRange](../../winscript/reference/iscriptentry-getrange.md)|エントリの開始位置と長さを返します。|  
|[IScriptEntry::GetSignature](../../winscript/reference/iscriptentry-getsignature.md)|@No__t_0 関数オブジェクトの型情報を返します。|  
|[IScriptEntry::GetText](../../winscript/reference/iscriptentry-gettext.md)|@No__t_0 スクリプトブロックに対応するテキスト、または `IScriptScriptlet` イベントハンドラーに含まれているソースコードを返します。|  
|[IScriptEntry::SetBody](../../winscript/reference/iscriptentry-setbody.md)|@No__t_0 スクリプトブロックの本文またはスクリプトレットの `IScriptScriptlet` に含まれるテキストを設定します。|  
|[IScriptEntry::SetItemName](../../winscript/reference/iscriptentry-setitemname.md)|@No__t_0 オブジェクトを識別する項目の名前を設定します。|  
|[IScriptEntry::SetName](../../winscript/reference/iscriptentry-setname.md)|1つのオブジェクト (関数など) を表すエントリの場合、によってオブジェクトの名前が設定されます。|  
|[IScriptEntry::SetSignature](../../winscript/reference/iscriptentry-setsignature.md)|@No__t_0 関数オブジェクトの型情報を設定します。|  
|[IScriptEntry::SetText](../../winscript/reference/iscriptentry-settext.md)|@No__t_0 スクリプトブロックに対応するテキスト、または `IScriptScriptlet` イベントハンドラーに含まれているソースコードを設定します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト作成インターフェイス](../../winscript/reference/active-script-authoring-interfaces.md)