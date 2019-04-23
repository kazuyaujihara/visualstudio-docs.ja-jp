---
title: -SafeMode (devenv.exe) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 94e8e87f4440644f76906a70ea09a46282b109c2
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59670356"
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] をセーフ モードで起動し、既定の環境とサービスのみを読み込みます。  
  
## <a name="syntax"></a>構文  
  
```  
devenv /SafeMode   
```  
  
## <a name="remarks"></a>解説  
 このスイッチでは、[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] が起動したときに、すべてのサード パーティ VSPackage を読み込まないようにするため、実行が安定したものになります。  
  
## <a name="description"></a>説明  
 次の例では、[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] をセーフ モードで起動します。  
  
## <a name="code"></a>コード  
  
```  
Devenv.exe /SafeMode  
```  
  
## <a name="see-also"></a>関連項目  
 [Devenv コマンド ライン スイッチ](../../ide/reference/devenv-command-line-switches.md)
