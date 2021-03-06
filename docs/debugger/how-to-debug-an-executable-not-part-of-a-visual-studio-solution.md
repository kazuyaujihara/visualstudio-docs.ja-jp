---
title: '方法: Visual Studio ソリューションの一部ではない実行可能ファイルのデバッグ |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], executables
- executable files, importing
- executable files, debugging outside of projects
ms.assetid: 3ea176e8-1ce5-42c4-b7a2-abe3a2765033
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ce84c4acdc2cf4324c76dbbf7fe0b39ca9715b3c
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279103"
---
# <a name="how-to-debug-an-executable-that-is-not-part-of-a-visual-studio-solution"></a>方法: Visual Studio ソリューションの一部ではない実行可能ファイルのデバッグ
実行可能 (.exe ファイル) をデバッグする場合もありますの一部を[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]プロジェクト。 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] の外部で作成された実行可能ファイルや、他の人から受け取った実行可能ファイルなどがその例です。  
  
この問題を解決するには、通常、Visual Studio 外部の実行可能ファイルを起動して、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] デバッガーを使用してそのファイルにアタッチします。 詳細については、次を参照してください。[実行中のプロセスにアタッチ](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)します。  
  
アプリケーションへのアタッチは、一部を手動で実行する必要があります。この処理には数秒かかります。 アプリケーションの起動時に発生する問題をデバッグする場合は、このわずかな遅延のため、アタッチが役に立ちません。 また、ユーザー入力を待たず、すぐに終了するプログラムをデバッグする場合は、アタッチしている時間がないこともあります。 あれば[!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)]と[!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)]インストールされている場合、このようなプログラムの EXE プロジェクトを作成することができます。

> [!NOTE]
>  EXE プロジェクトをサポートしていないプログラミング言語もあります。

Visual Studio ソリューションの一部ではない実行可能ファイルをデバッグするときに使用可能なデバッグ機能があります限られており、実行中の実行可能ファイルをアタッチする実行可能ファイルを追加するか、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ソリューション。

- ソース コードがある場合は、そのソース コードを [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] にインポートして、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] で実行可能ファイルのデバッグ ビルドを作成するのが最適です。
- せず、実行可能ファイルがビルドされている場合、ソース コードがあるない場合、[デバッグ情報](../debugger/how-to-set-debug-and-release-configurations.md)互換の形式では使用可能なデバッグ機能は非常に制限されています。 
  
### <a name="to-create-an-exe-project-for-an-existing-executable"></a>既存の実行可能ファイルの EXE プロジェクトを作成するには  
  
1.  **ファイル** メニューのをクリックして**オープン**選択**プロジェクト**します。  
  
2.  **プロジェクトを開く**ダイアログ ボックスで、ドロップダウン リストには、[次へ] をクリック、**ファイル名**ボックス、および選択**すべてのプロジェクト ファイル**します。  
  
3.  実行可能ファイルを見つけてクリックして**OK**します。  

    これにより、実行可能ファイルを格納する一時的なソリューションが作成されます。

5.  などの実行コマンドを選択して、実行可能ファイルを開始します。**開始**、から、**デバッグ**メニュー。    
  
### <a name="to-import-an-executable-into-a-visual-studio-solution"></a>Visual Studio ソリューションに実行可能ファイルをインポートするには  
  
1.  **ファイル**メニューで、**プロジェクトの追加**、 をクリックし、**既存のプロジェクト**します。  
  
2.  **既存プロジェクトの追加**ダイアログ ボックスで、ドロップダウン リストには、[次へ] をクリック、**ファイル名**ボックス、および選択**すべてのプロジェクト ファイル**します。  
  
3.  目的の実行可能ファイルを見つけ、選択します。  
  
4.  **[OK]** をクリックします。  
  
5.  などの実行コマンドを選択して、実行可能ファイルを開始します。**開始**、から、**デバッグ**メニュー。    
  
## <a name="see-also"></a>関連項目  
 [デバッガーの設定と準備](../debugger/debugger-settings-and-preparation.md)   
 [デバッガーのセキュリティ](../debugger/debugger-security.md)   
 [DBG ファイル](/previous-versions/visualstudio/visual-studio-2010/da528y14(v=vs.100))