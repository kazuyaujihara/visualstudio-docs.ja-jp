---
title: 'Office ソリューションを開発するコンピューターを構成する方法'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- prerequisites [Office development in Visual Studio]
- Office development in Visual Studio, installing tools
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 99dd7bea33fa534be8dceb0fb888ac50e23cd01d
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2019
ms.locfileid: "54865590"
---
# <a name="how-to-configure-a-computer-to-develop-office-solutions"></a>Office ソリューションを開発するコンピューターを構成する方法
  Visual Studio の Microsoft Office Developer Tools を使用できるように開発用コンピューターを構成するには、次のトピックの手順を実行します。これらの手順を実行するには、開発用コンピューターの管理特権を保持している必要があります。  
  
### <a name="to-configure-the-development-computer"></a>開発コンピューターを構成するには  
  
1.  Office Developer Tools が含まれているバージョンの Visual Studio をインストールします。 Office 開発者ツールは既定でインストールされます。インストールする機能を選択して、Visual Studio のインストールをカスタマイズする場合、**Microsoft Office Developer Tools** がセットアップ中に選択されていることを確認します。 Office Developer Tools を含む Visual Studio のバージョンの詳細については、[Office ソリューションを開発するコンピューターの構成](../vsto/configuring-a-computer-to-develop-office-solutions.md)を参照してください。  
  
2.  Visual Studio の Office Developer Tools によってサポートされているバージョンの Office をインストールします。詳細については、[Office ソリューションを開発するコンピューターの構成](../vsto/configuring-a-computer-to-develop-office-solutions.md)を参照してください。 
  
     インストールするバージョンの Office の PIA もインストールされることを確認してください。 PIA は、既定では Office と共にインストールされます。 Office セットアップを変更する場合、アプリケーションがターゲットにしたい **.NET プログラミング サポート**機能が選択されていることを確認します。  
  
3.  Visual Studio の英語版を所有しているが、 Windows の設定が英語以外の設定で使用している場合は、Windows と同じ言語で、[!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]のメッセージが見えるように [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]言語パックをインストールします。英語版以外の Visual Studio では、この言語パックが自動的にインストールされます。言語パックは、 [Microsoft ダウンロード センター](http://go.microsoft.com/fwlink/?LinkId=140386)で利用可能です。  
  
## <a name="see-also"></a>関連項目  
 [Office 開発の新機能](https://msdn.microsoft.com/bf054af2-c896-4723-aa15-6381145b14bb)   
 [はじめに &#40;Visual Studio での Office 開発&#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Visual Studio Tools for Office ランタイム再頒布可能パッケージをインストールする方法](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)   
 [Office プライマリ相互運用機能アセンブリをインストールする方法](../vsto/how-to-install-office-primary-interop-assemblies.md)  
