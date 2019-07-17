---
title: 使用した分離シェルを変更します。Vsct ファイル |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio shell, isolated mode%2C .vsct file
ms.assetid: 6d147c2d-10e9-400e-b8ce-5566287b41ba
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8c106a04e809e772ac3b8a77192fb2f101161e9c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194235"
---
# <a name="modifying-the-isolated-shell-by-using-the-vsct-file"></a>使用した分離シェルを変更します。Vsct ファイル
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 分離シェル プロジェクト、UI プロジェクトには、どのアプリケーション グループと個々 のコマンドは、アプリケーションで使用可能なを指定することができます、.vsct ファイルが含まれています。 次に、変更されていない .vsct ファイルからの抜粋を示します。  
  
```  
<!-- <Define name="No_WindowListCommand"/> -->  
<!-- <Define name="No_MoreWindowsCommand"/> -->  
<!-- <Define name="No_PaneNextPaneCommand"/> -->  
<!-- <Define name="No_PanePrevPaneCommand"/> -->  
```  
  
 既定では、ほとんどのコマンドおよびコマンド グループが含まれます。 コマンドやコマンドのグループを除外するには、そのコマンドまたはグループをコメント解除だけです。  
  
 たとえば、コメント解除と、[次へ] ウィンドウと前のウィンドウのコマンドを削除する、`No_PaneNextPaneCommand`と`No_PanePrevPaneCommand`エントリ。  
  
```  
  
<Define name="No_PaneNextPaneCommand"/> <Define name="No_PanePrevPaneCommand"/>  
  
```  
  
 詳細な例はこれらのカスタマイズを参照してください。[チュートリアル。分離シェル アプリケーションの基本的な作成](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)です。  
  
## <a name="referenced-files"></a>参照先のファイル  
 アプリケーションの既定の .vsct ファイルでは、次のファイルを参照します。 これらのファイルについては、Visual Studio SDK のインストール ディレクトリの \VisualStudioIntegration\Common\Inc\ サブディレクトリにあります。  
  
|ファイル|説明|  
|----------|-----------------|  
|wbids.h|Web 参照パッケージの UI の id。|  
|AppIDCmdUsed.vsct|コマンド テーブルの主な Visual Studio の UI 要素。|  
|EmulatorCmdUsed.vsct|Emacs および Brief エディターのエミュレーションの UI 要素のコマンド テーブル。|  
|Vsdebugguids.h|コマンドのオプション ページで、Visual Studio デバッガーの他の機能の Guid を定義します。|  
|VsDbgCmdUsed.vsct|デバッガーのコマンド テーブル。|  
  
 AppIDCmdUsed.vsct ファイルには、アプリケーションの .vsct ファイルで定義されているシンボルに基づいて Visual Studio の UI 要素が含まれています。  
  
 詳細については、次を参照してください。 [XML コマンド テーブルの設計 (します。Vsct) ファイル](../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)と[VSCT XML スキーマ リファレンス](../extensibility/vsct-xml-schema-reference.md)します。  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio の分離シェル](../extensibility/visual-studio-isolated-shell.md)
