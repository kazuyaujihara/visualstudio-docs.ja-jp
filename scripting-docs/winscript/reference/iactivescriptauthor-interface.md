---
title: IActiveScriptAuthor Interface |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptAuthor interface
ms.assetid: df1f454d-01ee-4beb-928b-48513d07365a
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ed0734fa48d58a5eae779c75c838c09215ed60a0
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72576165"
---
# <a name="iactivescriptauthor-interface"></a>IActiveScriptAuthor インターフェイス
IntelliSense や情報の照合順序など、作成サービスを表します。  
  
 @No__t_1 インターフェイスは、`IUnknown` から継承されたメソッドに加えて、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IActiveScriptAuthor::AddNamedItem](../../winscript/reference/iactivescriptauthor-addnameditem.md)|ルートレベルの項目の名前をスクリプト作成エンジンの名前空間に追加します。 *ルートレベルの項目*は、プロパティとメソッドを含むことができ、イベントソースも含むことができるオブジェクトです。|  
|[IActiveScriptAuthor::AddScriptlet](../../winscript/reference/iactivescriptauthor-addscriptlet.md)|ルートレベル `IScriptNode` オブジェクトの子としてコードスクリプトレットを追加します。 ホストでは、スクリプトレットの完全修飾名は、2つのレベルのみを持つことができます。|  
|[IActiveScriptAuthor::AddTypeLib](../../winscript/reference/iactivescriptauthor-addtypelib.md)|スクリプトの名前空間にタイプライブラリを追加します。|  
|[IActiveScriptAuthor::GetChars](../../winscript/reference/iactivescriptauthor-getchars.md)|要求された完了コンテキストの完了文字のセットを返します。|  
|[IActiveScriptAuthor::GetEventHandler](../../winscript/reference/iactivescriptauthor-geteventhandler.md)|指定された属性を持つスクリプトレットを返します。|  
|[IActiveScriptAuthor::GetInfoFromContext](../../winscript/reference/iactivescriptauthor-getinfofromcontext.md)|コードブロック内の指定された文字の型情報とアンカー位置を返します。 これにより、メンバーの IntelliSense、グローバルリスト、およびパラメーターのヒントに関する情報が提供されます。|  
|[IActiveScriptAuthor::GetLanguageFlags](../../winscript/reference/iactivescriptauthor-getlanguageflags.md)|言語情報を返します。|  
|[IActiveScriptAuthor::GetRoot](../../winscript/reference/iactivescriptauthor-getroot.md)|作成者のスクリプトツリーの `IScriptNode` ルートを返します。|  
|[IActiveScriptAuthor::GetScriptletTextAttributes](../../winscript/reference/iactivescriptauthor-getscriptlettextattributes.md)|スクリプトレットのテキスト属性を返します。|  
|[IActiveScriptAuthor::GetScriptTextAttributes](../../winscript/reference/iactivescriptauthor-getscripttextattributes.md)|スクリプトブロックのテキスト属性を返します。|  
|[IActiveScriptAuthor::IsCommitChar](../../winscript/reference/iactivescriptauthor-iscommitchar.md)|指定された文字が、アプリケーションによってステートメントの完了をコミットする必要があるかどうかを示す値を返します。|  
|[IActiveScriptAuthor::ParseScriptText](../../winscript/reference/iactivescriptauthor-parsescripttext.md)|スクリプトテキストを解析し、作成スクリプト作成エンジンにテキストを追加し、スクリプトブロックに対応する `IScriptEntry` オブジェクトを作成します。|  
|[IActiveScriptAuthor::RemoveNamedItem](../../winscript/reference/iactivescriptauthor-removenameditem.md)|スクリプト作成エンジンの名前空間から `NamedItem` オブジェクトを削除します。|  
|[IActiveScriptAuthor::RemoveTypeLib](../../winscript/reference/iactivescriptauthor-removetypelib.md)|スクリプト作成エンジンの名前空間からタイプライブラリを削除します。|  
  
## <a name="see-also"></a>関連項目  
 [アクティブ スクリプト作成インターフェイス](../../winscript/reference/active-script-authoring-interfaces.md)