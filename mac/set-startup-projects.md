---
title: Visual Studio for Mac で複数のスタートアップ プロジェクトを設定する
description: この記事では、実行時またはデバッグ時に開始する複数のプロジェクトを設定する方法について説明します。
author: sayedihashimi
ms.author: sayedha
ms.date: 02/21/2019
ms.topic: conceptual
ms.prod: visual-studio-mac
ms.assetid: fd354fff-ce6b-4505-a815-84a2311e39ba
ms.openlocfilehash: 65b44dddfdadcb7ef38332fa35443dbaeededb5d
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58152916"
---
# <a name="how-to-set-multiple-startup-projects"></a>方法: 複数のスタートアップ プロジェクトを設定する

Visual Studio for Mac では、ソリューションをデバッグまたは実行するときに、1 つまたは複数のプロジェクトを開始する方法を指定することができます。

## <a name="to-set-multiple-startup-projects"></a>複数のスタートアップ プロジェクトを設定するには

1.  **Solution Pad** で、ソリューション (最上位ノード) を選択します。

2. ソリューション ノードのコンテキスト (右クリック) メニューを選択し、**[スタートアップ プロジェクトの設定...]** を選択します。

   ![[スタートアップ プロジェクトの設定] コンテキスト メニュー](media/startup-proj-ctx-menu.png)

3. **[ソリューション実行構成の作成]** ダイアログが表示されます。 このダイアログでは、ご利用のソリューションに対して新しい名前の付いたソリューション実行構成が作成されます。 任意の名前を付けることができます。既定の名前は `Multiple Projects` です。

   ![[ソリューション実行構成の作成] ダイアログ](media/create-sln-run-config.png)

4. **[実行構成の作成]** をクリックします。 **[ソリューション オプション]** ダイアログが開き、新しいソリューション実行構成が選択されます。

   ![[ソリューション オプション] ダイアログ](media/sln-options-run-config-multi-projects.png)

5. Visual Studio for Mac からアプリケーションをデバッグまたは実行するときに起動するプロジェクトを選択します。

   ![構成した実行構成を含む [ソリューション オプション] ダイアログ](media/sln-options-run-config-multi-projects-configured.png)

6. **[OK]** をクリックします。 ダイアログが終了すると、新しいソリューション実行構成がアクティブな実行構成として設定されます。

   ![デバッグまたは実行時に複数のプロジェクトが開始するように構成されたソリューション](media/startup-project-configured.png) 2 つのプロジェクトが **Solution Pad** 内で**ボールド**表示されているので、この 2 つが開始するように構成されていることがわかります。 ツールバーでは、新しい実行構成が現在のソリューション実行構成として構成されます。

## <a name="next-steps"></a>次の手順

- [Visual Studio for Mac のコンパイルとビルド](compiling-and-building.md)
- [ビルド構成について](configurations.md)