---
title: IDispError インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDispError interface
ms.assetid: 3dc7b55e-94ba-4669-b20a-1e011f2d07cf
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c67ff6e458f8350ef36a8a454e017b3ce6ea114
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144928"
---
# <a name="idisperror-interface"></a>IDispError インターフェイス
詳細なコンテキスト エラー情報を提供します。  
  
> [!NOTE]
>  このインターフェイスが実装されていません。  
  
 継承されたメソッドだけでなく`IUnknown`、`IDispError`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDispError::QueryErrorInfo](../../winscript/reference/idisperror-queryerrorinfo.md)|特定の種類のエラー情報を取得します。|  
|[IDispError::GetNext](../../winscript/reference/idisperror-getnext.md)|次の取得`IDispError`オブジェクト。|  
|[IDispError::GetHresult](../../winscript/reference/idisperror-gethresult.md)|エラー コードを取得、`IDispError`オブジェクト。|  
|[IDispError::GetSource](../../winscript/reference/idisperror-getsource.md)|クラスまたはエラーが発生したアプリケーションの言語に依存するプログラム id を返します。|  
|[IDispError::GetHelpInfo](../../winscript/reference/idisperror-gethelpinfo.md)|ヘルプ ファイルのパスと可能な場合、エラーを説明するトピックのコンテキスト ID を返します。|  
|[IDispError::GetDescription](../../winscript/reference/idisperror-getdescription.md)|エラーの説明テキストを返します。|