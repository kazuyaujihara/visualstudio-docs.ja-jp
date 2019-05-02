---
title: リモート コンピューター (レガシ) からワークフローのデバッグ |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- workflows, debugging remotely
- debugging workflows, remotely
- remote debugging, workflows
- debugging, remote
ms.assetid: 44eaec8f-9959-4ae7-a374-670946f933c1
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f37e2f1d785399283e9da8f4ecb853f0728d9830
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62976943"
---
# <a name="debugging-workflows-from-a-remote-computer-legacy"></a>リモート コンピューターからのワークフローのデバッグ (レガシ)
このトピックでは、従来の [!INCLUDE[wf](../includes/wf-md.md)]を使用して作成された、リモートにある従来の [!INCLUDE[wfd1](../includes/wfd1-md.md)] アプリケーションをデバッグする方法について説明します。 アプリケーションが [!INCLUDE[wfd2](../includes/wfd2-md.md)] または [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] を対象とする必要がある場合は、従来の[!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)]を使用します。  
  
 インストールするときに[!INCLUDE[vs_current_long](../includes/vs-current-long-md.md)]をインストールするコンポーネントのインストール オプションの 1 つは、 [!INCLUDE[vs_current_long](../includes/vs-current-long-md.md)] Debugger for[!INCLUDE[wf](../includes/wf-md.md)]します。 これにより、リモート デバッグ コンポーネントがインストールされます。 リモート デバッグ コンポーネントは、リモート ワークフロー デバッグの対象となるコンピューター上にインストールされる必要があります。  
  
 さらに、リモート コンピューター上のデバッグ対象である従来のワークフローのワークフロー定義を格納するアセンブリは、デバッグ元のローカル コンピューターのグローバル アセンブリ キャッシュ (GAC) にインストールされなければなりません。 たとえば、従来のワークフローがリモート コンピューター A で実行され、ローカル コンピューター B からそれをデバッグする場合には、ワークフロー定義はコンピューター B の GAC に存在する必要があります。これにより、デザイナーは、リモート コンピューター A で実行されるワークフローのワークフロー マークアップを逆シリアル化してコンピューター B に表示できます。グローバル アセンブリ キャッシュの詳細については、MSDN ライブラリを参照してください。  
  
 [!INCLUDE[wf2](../includes/wf2-md.md)] のリモート デバッグは、他の [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] コンポーネントのリモート デバッグと同じように機能します。 詳細については、次を参照してください。 [!INCLUDE[vs_current_long](../includes/vs-current-long-md.md)] 、MSDN ライブラリでのリモート デバッグ。  
  
## <a name="see-also"></a>関連項目  
 [従来のワークフローのデバッグ](../workflow-designer/debugging-legacy-workflows.md)