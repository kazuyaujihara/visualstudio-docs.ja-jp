---
title: '方法: プロファイル ツールの ETW レポートを作成する | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: bf5547b3-f6c7-4989-9d47-2fe4f1261444
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6b172ffbf481ea077d099288b3b79254b89b13a5
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63432742"
---
# <a name="how-to-create-a-profiling-tools-etw-report"></a>方法: プロファイリング ツールの ETW レポートを作成します。
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Windows イベント トレーシング (ETW) レポートには、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] プロファイル ツールのパフォーマンス セッションで記録された ETW イベントが一覧表示されます。 ETW データはバイナリ (.etl) ファイルで収集されます。 このレポートの詳細については、「[ETW (Event Tracing for Windows) レポート](../profiling/event-tracing-for-windows-etw-report.md)」を参照してください。  
  
> [!NOTE]
> [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] の場合、インターフェイスに ETW レポートを表示できません。  
  
- [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] のインターフェイスを利用して ETW データを収集する方法については、「[方法:Event Tracing for Windows (ETW) のデータ収集](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)します。  
  
- コマンド プロンプトから ETW データを収集する方法については、「[VSPerfCmd](../profiling/vsperfcmd.md)」と「[イベント](../profiling/events-vsperfcmd.md)」を参照してください。  
  
  ETW レポートは **VSReport/summary:etw** コマンドを利用して生成します。 ETW データを含む .etl は、プロファイル データ (.vsp または .vsps) ファイルと同じディレクトリに置く必要があります。 既定では、レポートはコンマ区切り値 (.csv) ファイルとして生成されます。 詳細については、「[VSPerfReport](../profiling/vsperfreport.md)」を参照してください。  
  
### <a name="to-generate-an-etw-report"></a>ETW レポートを生成するには  
  
- **[コマンド プロンプト]** ウィンドウで、次のコマンド ラインを入力します。  
  
     *ToolsPath* **VSPerfReport** *VSPFile*  **/Summary:ETW [/Xml]**  
  
    |||  
    |-|-|  
    |*ToolsPath*|プロファイリング ツール ユーティリティのパス。 詳細については、「[コマンド ライン ツールへのパスの指定](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)」をご覧ください。|  
    |*VSPFile*|プロファイル データ (.vsp または .vsps) ファイル。 完全パスまたは部分パスで指定できます。|  
    |Xml|XML で書式設定されているレポートを生成します。|
