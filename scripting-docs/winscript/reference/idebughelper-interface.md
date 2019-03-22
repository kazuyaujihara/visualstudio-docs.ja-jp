---
title: IDebugHelper インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugHelper interface
ms.assetid: ef5691e0-1d82-42c2-997c-888e31c478dd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d1708b742a484a2e7d6d48cf759f15c08711e13d
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58148061"
---
# <a name="idebughelper-interface"></a>IDebugHelper インターフェイス
オブジェクト ブラウザーと単純な接続ポイントのためのファクトリとして機能します。 プロセス デバッグ マネージャー (PDM) は、スクリプト エンジンによって使用される、このインターフェイスを実装します。  
  
 継承されたメソッドだけでなく`IUnknown`、`IDebugHelper`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugHelper::CreatePropertyBrowser](../../winscript/reference/idebughelper-createpropertybrowser.md)|バリアント型をラップするプロパティ ブラウザーを返します。|  
|[IDebugHelper::CreatePropertyBrowserEx](../../winscript/reference/idebughelper-createpropertybrowserex.md)|バリアントをラップし、VARIANT 値または VARTYPE 型の文字列にカスタムの変換では、プロパティ ブラウザーを返します。|  
|[IDebugHelper::CreateSimpleConnectionPoint](../../winscript/reference/idebughelper-createsimpleconnectionpoint.md)|ラップするイベント インターフェイスを返します、指定された`IDispatch`オブジェクト。|