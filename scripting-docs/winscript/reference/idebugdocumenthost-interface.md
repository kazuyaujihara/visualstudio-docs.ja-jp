---
title: IDebugDocumentHost インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentHost interface
ms.assetid: 2fed4220-b6a2-47c6-bf28-daad7dd5c42d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 226e2700b471cd34496682d233e57946e124ff3b
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58155668"
---
# <a name="idebugdocumenthost-interface"></a>IDebugDocumentHost インターフェイス
構文の色分け、デバッガーなどのホスト固有の機能を公開します。 `IDebugDocumentHelper::SetDebugDocumentHost`メソッドは引数としてこのインターフェイスを受け取ります。  
  
 継承されたメソッドだけでなく`IUnknown`、`IDebugDocumentHost`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugDocumentHost::GetDeferredText](../../winscript/reference/idebugdocumenthost-getdeferredtext.md)|使用して追加された文字の範囲を返します`IDebugDocumentHelper::AddDeferredText`、元のホスト ドキュメント。|  
|[IDebugDocumentHost::GetScriptTextAttributes](../../winscript/reference/idebugdocumenthost-getscripttextattributes.md)|ドキュメントのテキストのブロックをテキスト属性を返します。|  
|[IDebugDocumentHost::OnCreateDocumentContext](../../winscript/reference/idebugdocumenthost-oncreatedocumentcontext.md)|新しいドキュメント コンテキストが作成されると、により、必要に応じて、新しいコンテキストを制御するオブジェクトを取得するホストをホストに通知します。|  
|[IDebugDocumentHost::GetPathName](../../winscript/reference/idebugdocumenthost-getpathname.md)|ドキュメントのソース ファイルの完全なパス (ファイル名を含む) を返します。|  
|[IDebugDocumentHost::GetFileName](../../winscript/reference/idebugdocumenthost-getfilename.md)|パス情報がない場合、ドキュメントの名前を返します。|  
|[IDebugDocumentHost::NotifyChanged](../../winscript/reference/idebugdocumenthost-notifychanged.md)|ドキュメントのソース ファイルが保存されていると、その内容を更新する必要があるホストに通知します。|