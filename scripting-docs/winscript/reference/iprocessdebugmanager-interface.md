---
title: IProcessDebugManager インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IProcessDebugManager interface
ms.assetid: b6ecb2bd-a4d1-4857-9232-036c154d0cb1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d68c044cdc3d523841cc56814b8ca34bcd8aa037
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62944798"
---
# <a name="iprocessdebugmanager-interface"></a>IProcessDebugManager インターフェイス
プロセス デバッグ マネージャーの主インターフェイスです。 このインターフェイスは、プロセスの仮想アプリケーションを作成、追加、または削除することができます。 スタック フレームとアプリケーションのスレッドを列挙します。  
  
 継承されたメソッドだけでなく`IUnknown`、`IProcessDebugManager`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IProcessDebugManager::CreateApplication](../../winscript/reference/iprocessdebugmanager-createapplication.md)|このアプリケーションの新しいデバッグ アプリケーション オブジェクトを作成します。|  
|[IProcessDebugManager::GetDefaultApplication](../../winscript/reference/iprocessdebugmanager-getdefaultapplication.md)|現在のプロセスの既定のアプリケーション オブジェクトを返します。|  
|[IProcessDebugManager::AddApplication](../../winscript/reference/iprocessdebugmanager-addapplication.md)|実行中のアプリケーションには、マシン デバッグ マネージャーの一覧にアプリケーションを追加します。|  
|[IProcessDebugManager::RemoveApplication](../../winscript/reference/iprocessdebugmanager-removeapplication.md)|実行中のアプリケーションを削除します。 アプリケーションの一覧。|  
|[IProcessDebugManager::CreateDebugDocumentHelper](../../winscript/reference/iprocessdebugmanager-createdebugdocumenthelper.md)|このアプリケーションの新しいデバッグ ドキュメント ヘルパーを作成します。|