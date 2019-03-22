---
title: IDebugSessionProvider インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugSessionProvider interface
ms.assetid: 1b898423-7af9-44f5-8dda-987005309c99
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fe73901d92cb42675ff9ec981bd9b90dcca5d546
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58148988"
---
# <a name="idebugsessionprovider-interface"></a>IDebugSessionProvider インターフェイス
デバッガー ホストと言語を有効にする IDE によって提供される主要なインターフェイスでは、デバッグを開始します。 実行中のアプリケーションのデバッグ セッションを確立します。 このインターフェイスは、マシン デバッグ マネージャーによって実装されます。  
  
 継承されたメソッドだけでなく`IUnknown`、`IDebugSessionProvider`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugSessionProvider::StartDebugSession](../../winscript/reference/idebugsessionprovider-startdebugsession.md)|指定したアプリケーションのデバッグ セッションを開始します。|