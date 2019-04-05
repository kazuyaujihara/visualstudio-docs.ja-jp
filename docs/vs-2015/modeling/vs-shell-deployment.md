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
ms.openlocfilehash: 6c79a8a0558594e8981959750ebd348b6f9f4d60
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58974026"
---
# <a name="vs-shell-deployment"></a>VS Shell 配置
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

分離のシェルでは、Visual Studio を確認できます。 機能、ドメイン固有言語およびそのソリューションを表示する方法と対話する必要があります。 Visual Studio 分離シェルの詳細については、次を参照してください。[分離シェルのカスタマイズ](../extensibility/customizing-the-isolated-shell.md)します。 分離シェルをカスタマイズする方法の詳細を検索する[分離シェルのカスタマイズ](http://msdn.microsoft.com/d75463cd-1155-42e4-8b7a-046ed6becbbf)します。  
  
### <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>配置ターゲットとして Visual Studio Shell を設定するには  
  
1.  **DslPackage**プロジェクトを開き、 **source.extension.tt**します。  
  
2.  `<SupportedProducts>`を挿入します。  
  
    ```  
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>  
    ```  
  
     置換*MyIsolatedShell*分離シェルのパッケージの名前に置き換えます。
