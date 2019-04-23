---
title: -Updateconfiguration (devenv.exe) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /updateconfiguration Devenv switch
- Devenv, /updateconfiguration switch
- updateconfiguration Devenv switch
ms.assetid: 9a1084cc-8b68-4ccc-aaea-f95939164338
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9ffc9410d64f58fff771a0e9b251ee1131eaea5e
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59670031"
---
# <a name="updateconfiguration-devenvexe"></a>/Updateconfiguration (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] にシステム上の [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] パッケージをマージさせ、MEF キャッシュに変更がないかを確認することを通知します。  
  
## <a name="syntax"></a>構文  
  
```  
devenv /updateconfiguration  
```  
  
## <a name="remarks"></a>解説  
 VSIX パッケージをインストールすると、[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ではこのコマンドが自動的に実行されます。 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] が MEF キャッシュを更新するように、ファイルの修正プログラムを適用した後に `devenv.exe /updateconfiguration` を実行する必要があります。 これにより、修正が適切かどうかを評価することができます。  
  
## <a name="example"></a>例  
 次のコマンド ラインでは、[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] にシステム上の [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] パッケージをマージさせ、MEF キャッシュに変更がないかを確認させます。  
  
```  
Devenv.exe /updateconfiguration  
```  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio での開発設定のカスタマイズ](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Devenv コマンド ライン スイッチ](../../ide/reference/devenv-command-line-switches.md)
