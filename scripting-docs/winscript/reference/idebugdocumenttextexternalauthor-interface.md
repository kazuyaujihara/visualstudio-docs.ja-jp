---
title: IDebugDocumentTextExternalAuthor インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentTextExternalAuthor interface
ms.assetid: 0b04de1b-f922-4526-af4e-c0af2b7c1ce4
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 60fb0d68d8052990fcc1783f86d0213b714dbfc9
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144707"
---
# <a name="idebugdocumenttextexternalauthor-interface"></a>IDebugDocumentTextExternalAuthor インターフェイス
安全にドキュメント ソース ファイルが変更されたときに通知することにより、ファイルベースのデバッガーのドキュメントを編集する外部エディターを使用できます。  
  
 継承されたメソッドだけでなく`IUnknown`、`IDebugDocumentTextExternalAuthor`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugDocumentTextExternalAuthor::GetPathName](../../winscript/reference/idebugdocumenttextexternalauthor-getpathname.md)|ドキュメントの完全なパスとファイル名を返します。|  
|[IDebugDocumentTextExternalAuthor::GetFileName](../../winscript/reference/idebugdocumenttextexternalauthor-getfilename.md)|パス情報がない場合、ドキュメントの名前を返します。|  
|[IDebugDocumentTextExternalAuthor::NotifyChanged](../../winscript/reference/idebugdocumenttextexternalauthor-notifychanged.md)|ドキュメントのソースが変更されたことをホストに通知します。|