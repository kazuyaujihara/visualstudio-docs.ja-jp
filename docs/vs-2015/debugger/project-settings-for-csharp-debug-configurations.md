---
title: プロジェクトの c# デバッグ構成の設定 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debug configurations, C#
- debugging [J#], debugger settings
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- projects [Visual Studio], debug configurations
- project configurations, debug
- debugging [C#], debugger settings
- debug configurations, J#
ms.assetid: e30ca810-66e9-4d6e-9cf6-9f285cd0b100
caps.latest.revision: 25
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4f98441afbe8056fa01a11d7265447a293cd10fa
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446159"
---
# <a name="project-settings-for--c-debug-configurations"></a>C# デバッグ構成のプロジェクト設定
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

C# デバッグ構成でのプロジェクトの設定を変更することができます、**プロパティ ページ**ウィンドウで説明したよう[デバッグ構成とリリース構成](../debugger/how-to-set-debug-and-release-configurations.md)します。 次の表は、**[プロパティ ページ]** ウィンドウのデバッガー関連の設定の場所を示しています。  
  
> [!WARNING]
> このトピックは Windows ストア アプリには適用されません。 参照してください[(VB、c#、C++ および XAML) は、デバッグ セッションを開始](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
## <a name="BKMK_Debug_tab"></a> [デバッグ] タブ  
  
|**設定**|**説明**|  
|-----------------|---------------------|  
|**構成**|アプリケーションをコンパイルするためのモードを設定します。 **[Active (Debug)]\(アクティブ (デバッグ)\)**、**[デバッグ]**、**[リリース]**、**[すべての構成]** から選択します。|  
|**開始動作**|[デバッグ] メニューの [開始] を選択したときに発生するアクションを指定します。<br /><br /> -   既定値は **[プロジェクトの開始]** で、デバッグのスタートアップ プロジェクトを起動します。 詳細については、次を参照してください。[スタートアップ プロジェクトの選択](http://msdn.microsoft.com/222e3f32-a6fe-4941-bf37-6b2a921129fd)します。<br />-   **[外部プログラムの開始]** では、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] プロジェクトに含まれないプログラムを起動してアタッチできます。 詳細については、次を参照してください。[実行中のプログラムへのアタッチ](http://msdn.microsoft.com/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4)します。<br />-   **[ブラウザーを開始時に使用する URL]** は、Web アプリケーションのデバッグを有効にします。|  
|**コマンド ライン引数**|デバッグするプログラムのコマンド ライン引数を指定します。 コマンド名は、[外部プログラムの開始] に指定されたプログラム名です。 [開始動作] が [URL の開始] に設定されている場合、コマンド ライン引数は指定できません。|  
|**作業ディレクトリ**|デバッグするプログラムの作業ディレクトリを指定します。 [!INCLUDE[csprcs](../includes/csprcs-md.md)] では、作業ディレクトリはアプリケーションが起動されるディレクトリであり、既定では \bin\debug です。|  
|**リモート コンピューターの使用**|デバッグのため、アプリケーションが実行されるリモート マシンの名前または[Msvsmon サーバー名](http://msdn.microsoft.com/library/55b60ce7-834b-4e83-a10e-fe4248260a4c)します。 リモート コンピューター上の EXE ファイルの場所は、[構成プロパティ] フォルダー、[ビルド] カテゴリ内の [出力パス] プロパティで指定します。 また、EXE ファイルがリモート コンピューターの共有ディレクトリにあることも必要です。|  
|**アンマネージ コード デバッグを有効にする**|マネージド アプリケーションからネイティブ (アンマネージド) Win32 コードの呼び出しをデバッグできます。|  
|**SQL Server デバッグを有効にする**|SQL Server データベース オブジェクトのデバッグを許可します。|  
  
## <a name="BKMK_Build_tab"></a> [ビルド] タブ  
  
|設定|説明|  
|-------------|-----------------|  
|**条件付きコンパイル シンボル:**|定数 DEBUG および定数 TRACE をここで定義します。<br /><br /> これらの定数により、[Debug クラス](https://msdn.microsoft.com/library/system.diagnostics.debug.aspx)と [Trace クラス](https://msdn.microsoft.com/library/system.diagnostics.trace.aspx)の条件付きコンパイルが有効になります。 これらの定数を定義すると、Debug クラスと Trace クラスのメソッドによって[出力ウィンドウ](../ide/reference/output-window.md)に出力が生成されます。 これらの定数を定義しない場合、Debug クラスと Trace クラスのメソッドはコンパイルされず、出力も生成されません。<br /><br /> デバッグは通常、プログラムのデバッグ バージョンで定義され、リリース バージョンで定義されていません。<br />トレースは、通常、デバッグとリリースの両方のバージョンで定義します。|  
|**コードの最適化**|デバッグ バージョンでは、最適化されたコードにだけ現れるバグを見つけた場合に限って、この設定をオンにすることをお勧めします。 最適化されたコードは、命令がソース ウィンドウのステートメントに直接対応していないため、デバッグが困難です。|  
|**出力パス:**|通常は、デバッグ用の bin\Debug に設定します。|  
  
## <a name="see-also"></a>関連項目  
 [デバッガーの設定と準備](../debugger/debugger-settings-and-preparation.md)
