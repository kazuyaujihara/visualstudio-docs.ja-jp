---
title: VS Shell 配置 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: be8f2ffe-a322-4ac0-9c9e-873bd28e5d5e
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5bfe88d7e7d742eb67273d307c3a8e72e9a85833
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65704048"
---
# <a name="vs-shell-deployment"></a>VS Shell 配置
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

分離のシェルでは、Visual Studio を確認できます。 機能、ドメイン固有言語およびそのソリューションを表示する方法と対話する必要があります。 Visual Studio 分離シェルの詳細については、次を参照してください。[分離シェルのカスタマイズ](../extensibility/customizing-the-isolated-shell.md)します。 分離シェルをカスタマイズする方法の詳細を検索する[分離シェルのカスタマイズ](https://msdn.microsoft.com/d75463cd-1155-42e4-8b7a-046ed6becbbf)します。  
  
### <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>配置ターゲットとして Visual Studio Shell を設定するには  
  
1. **DslPackage**プロジェクトを開き、 **source.extension.tt**します。  
  
2. `<SupportedProducts>`を挿入します。  
  
    ```  
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>  
    ```  
  
     置換*MyIsolatedShell*分離シェルのパッケージの名前に置き換えます。
