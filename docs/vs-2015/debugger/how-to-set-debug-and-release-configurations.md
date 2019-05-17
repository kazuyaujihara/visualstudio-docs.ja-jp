---
title: '方法: セットのデバッグ構成とリリースの構成 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.builds
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- configurations, release
- build configurations, release
- projects [Visual Studio], release configurations
- debugging [Visual Studio], release configurations
- release builds, changing settings
- debug builds
- debug builds, switching to release build
- debug builds, changing configuration settings
- debugging [Visual Studio], debug configurations
- projects [Visual Studio], debug configurations
- build configurations, debug
- debug configurations
- release builds, switching to debug build
- Visual Basic projects, debug and release builds
ms.assetid: 57b6bbb7-f2af-48f7-8773-127d75034ed2
caps.latest.revision: 48
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4984355c12a92529a943fe6778740ac2d7f522f8
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65703652"
---
# <a name="how-to-set-debug-and-release-configurations"></a>方法: セットのデバッグ構成とリリース構成
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio プロジェクトでは、ご使用のプログラムに対応するリリースとデバッグ構成を個別に用意しています。 名前が示すように、デバッグ バージョンはデバッグ用、リリース バージョンは最終リリース配布用のビルドです。  
  
 プログラムのデバッグ構成のコンパイルでは、シンボリック デバッグ情報が完全に含まれ、最適化は行われません。 ソース コードと生成された命令の関係は非常に複雑であり、最適化を行うとデバッグが困難になるためです。  
  
 プログラムのリリース構成は、シンボリック デバッグ情報を含まず、完全に最適化されます。 使用しているコンパイラ オプションによっては、デバッグ情報が PDB ファイル内に生成される場合があります。 PDB ファイルを作成すると、後でリリース バージョンをデバッグする際に大きく役立つことがあります。  
  
 ビルド構成の詳細については、「[ビルド構成について](../ide/understanding-build-configurations.md)」を参照してください。  
  
 ビルド構成を変更することができます、**ビルド**メニュー、ツールバーで、またはプロジェクトのプロパティ ページ。 プロジェクト プロパティ ページは、言語固有のページです。 次の手順では、メニューとツールバーからビルド構成を変更する方法を示します。 各種言語のプロジェクトでビルド構成を変更する方法の詳細については、以下の「関連項目」を参照してください。  
  
### <a name="to-change-the-build-configuration"></a>ビルド構成を変更するには  
  
1. [ビルド] メニュー: をクリックして**ビルド/Configuration Manager**を選択し、**デバッグ**または**リリース**します。  
  
2. ツールバーで、いずれかを選択**デバッグ**または**リリース**から、**ソリューション構成**ボックスの一覧。  
  
     ![ツールバーのビルド構成](../debugger/media/toolbarbuildconfiguration.png "ToolbarBuildConfiguration")  
  
     このツールバーは、Express Edition では使用できません。 使用することができます、**ソリューションのビルド F6**と**デバッグの開始 F5**構成を選択するメニュー項目。  
  
## <a name="see-also"></a>関連項目  
 [デバッガーの設定と準備](../debugger/debugger-settings-and-preparation.md)   
 [C++ デバッグ構成のプロジェクト設定](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [C# デバッグ構成のプロジェクト設定](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Visual Basic デバッグ構成のプロジェクト設定](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [方法: 作成し、構成の編集](../ide/how-to-create-and-edit-configurations.md)   
 [デバッグ プロジェクト構成およびリリース プロジェクト構成](https://msdn.microsoft.com/0440b300-0614-4511-901a-105b771b236e)
