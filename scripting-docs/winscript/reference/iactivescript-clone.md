---
title: 'IActiveScript:: Clone |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.Clone
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_Clone
ms.assetid: aa000b2a-7085-448d-a422-f7adac7851cb
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fbaad29cb31af26a0f26a1c679a900192fc77041
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72575798"
---
# <a name="iactivescriptclone"></a>IActiveScript::Clone
現在のスクリプトエンジン (現在の実行状態を除く) を複製し、現在のスレッドにサイトを持たない読み込み済みのスクリプトエンジンを返します。 この新しいスクリプトエンジンのプロパティは、初期化された状態に遷移した場合、元のスクリプトエンジンが存在するプロパティと同じになります。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Clone(  
    IActiveScript **ppscript  // receives pointer to IActiveScript  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppscript`  
 入出力複製されたスクリプトエンジンの[IActiveScript](../../winscript/reference/iactivescript.md)インターフェイスへのポインターを受け取る変数のアドレス。 ホストはサイトを作成し、新しいスクリプトエンジンで[IActiveScript:: SetScriptSite](../../winscript/reference/iactivescript-setscriptsite.md)メソッドを呼び出す必要があります。その後、初期化された状態になり、使用できるようになります。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_NOTIMPL`|このメソッドはサポートされていません。|  
|`E_POINTER`|無効なポインターが指定されました。|  
|`E_UNEXPECTED`|この呼び出しは想定されていませんでした (たとえば、スクリプトエンジンがまだ読み込まれていないか、初期化されていません)。|  
  
## <a name="remarks"></a>Remarks  
 @No__t_0 メソッドは、`IPersist*::Save`、`CoCreateInstance`、および `IPersist*::Load` の最適化であるため、新しいスクリプトエンジンの状態は、元のスクリプトエンジンの状態が保存され、新しいスクリプトエンジンに読み込まれた場合と同じである必要があります。 複製されたスクリプトエンジンでは名前付きの項目が複製されますが、各項目の特定のオブジェクトポインターは忘れられ、 [IActiveScriptSite:: GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md)メソッドを使用して取得されます。 これにより、スレッドごとのエントリポイント (アパートメントモデル) と同一のオブジェクトモデルを使用できます。  
  
 このメソッドは、同じスクリプトの複数のインスタンスを実行できるマルチスレッドサーバーホストに使用されます。 スクリプトエンジンは `E_NOTIMPL` を返すことがあります。この場合、ホストは、永続的な状態を複製し、`IPersist*` インターフェイスを使用してスクリプトエンジンの新しいインスタンスを作成することで、同じ結果を得ることができます。  
  
 このメソッドは非ベースのスレッドから呼び出すことができます。この場合、非ベースのコールアウトによってオブジェクトをホストするか、 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)インターフェイスを使用することはできません。  
  
## <a name="see-also"></a>関連項目  
 [IActiveScript](../../winscript/reference/iactivescript.md)