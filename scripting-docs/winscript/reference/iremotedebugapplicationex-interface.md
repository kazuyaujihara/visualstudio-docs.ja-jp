---
title: IRemoteDebugApplicationEx インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplicationEx Interface
ms.assetid: 8e16164d-dbb2-4488-9507-25ae34f343dc
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab9e25a28ade1ac73b9e4837dae61e2d91f24c45
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144408"
---
# <a name="iremotedebugapplicationex-interface"></a>IRemoteDebugApplicationEx インターフェイス
実行中のアプリケーションを表します。 オペレーティング システムのプロセスに対応する必要はありません。 通常、デバッガーはデバッグ用のアプリケーションを対象とします。 プロセス デバッグ マネージャーは、通常、アプリケーション オブジェクトを実装します。  
  
 継承されたメソッドだけでなく`IUnknown`、`IRemoteDebugApplicationEx`インターフェイスは、次のメソッドを公開します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IRemoteDebugApplicationEx:GetHostPid](../../winscript/reference/iremotedebugapplicationex-gethostpid.md)|ホスト アプリケーションのプロセス ID を返します。|  
|GetHostMachineName|ホスト アプリケーションが実行されているコンピューターの名前を返します。|  
|[IRemoteDebugApplicationEx:SetLocale](../../winscript/reference/iremotedebugapplicationex-setlocale.md)|デバッガーのローカライズ用の言語を設定します。|  
|[IRemoteDebugApplicationEx:ForceStepMode](../../winscript/reference/iremotedebugapplicationex-forcestepmode.md)|シングル ステップ モードにデバッガーを強制します。|  
|[IRemoteDebugApplicationEx:RevokeBreak](../../winscript/reference/iremotedebugapplicationex-revokebreak.md)|Break コマンドを取り消します。|  
|SetProxyBlanketAndAddRef|Windows 95 ベースのオペレーティング システムからのリモート デバッグとの互換性を確保するには、デバッガー オブジェクトのプロキシでの COM セキュリティ情報を更新します。|  
|ReleaseFromSetProxyBlanket|SetProxyBlanketAndAddRef から AddRef をリリースします。|