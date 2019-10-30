---
title: マネージ参照 (Visual Studio での Office 開発)
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- reference [Office development in Visual Studio], 2007 Microsoft Office system
- Office development in Visual Studio, reference
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 137031202075d1c646cc7415042dd8d6eab72b78
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72985766"
---
# <a name="managed-reference-office-development-in-visual-studio"></a>マネージ参照 (Visual Studio での Office 開発)
  このセクションには、 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] または [!INCLUDE[net_v45](includes/net-v45-md.md)]を対象とする Office プロジェクトで使用される名前空間と型についての API リファレンス ドキュメントが含まれています。 .NET Framework 3.5 を対象とする Office プロジェクトで使用される名前空間と型に関する API リファレンスドキュメントについては、Visual Studio ドキュメントの「[マネージリファレンス (Visual studio での office 開発)」の次のリファレンスセクションを参照してください。)](managed-reference-office-development-in-visual-studio.md).

[!include[Add-ins note](includes/addinsnote.md)]

## <a name="in-this-section"></a>このセクションの内容
 <xref:Microsoft.Office.Tools>

 Office ソリューションのプログラミングに共通するクラスが含まれています。 これには、VSTO アドインの基底クラス、VSTO アドインにカスタム作業ウィンドウを作成するクラス、Excel および Word ソリューションにスマート タグを作成するクラス、ドキュメント レベルのカスタマイズで操作ウィンドウを作成するクラスが含まれます。

 <xref:Microsoft.Office.Tools.Excel>

 Excel のソリューションで使用できるホスト コントロールとホスト項目が含まれています。

 <xref:Microsoft.Office.Tools.Excel.Controls>

 Excel のソリューションで使用できる Excel コントロールと Windows フォーム コントロールが含まれています。

 <xref:Microsoft.Office.Tools.Outlook>

 Outlook 用 VSTO アドインで使用されるクラスが含まれています。カスタム フォーム領域の作成に使用されるクラスも含まれています。

 <xref:Microsoft.Office.Tools.Ribbon>

 リボン デザイナーを使用して作成されたリボンのカスタマイズを、プログラムによって変更するために使用されるクラスが含まれています。

 <xref:Microsoft.Office.Tools.Word>

 Word のソリューションで使用できるホスト コントロールとホスト項目が含まれています。

 <xref:Microsoft.Office.Tools.Word.Controls>

 Word のソリューションで使用できる Word コントロールと Windows フォーム コントロールが含まれています。

 <xref:Microsoft.VisualStudio.Tools.Applications>

 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> クラスと、関連するキャッシュ データ クラスのセットが含まれています。 これらのクラスは、Microsoft Office がインストールされていないコンピューター上のドキュメント レベルのカスタマイズの特定部分を変更するために使用できます。

 <xref:Microsoft.VisualStudio.Tools.Applications.Deployment>

 <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> インターフェイス (Office ソリューションの *配置後アクション* の作成用に実装可能)、Office ソリューションのインストール中にスローされる可能性のある例外、Visual Studio インフラストラクチャの一部である他の API が含まれています。

 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime>

 [!INCLUDE[vsto_runtime](includes/vsto-runtime-md.md)]によってスローされる可能性のある大部分の例外、ドキュメント レベルのカスタマイズでデータのキャッシュに使用できるクラス、Visual Studio インフラストラクチャの一部であるその他の API が含まれています。

 <xref:Microsoft.VisualStudio.Tools.Office.BuildTasks>

 Office プロジェクトのビルドに使用される MSBuild タスク クラスが含まれています。

## <a name="see-also"></a>関連項目
- [Visual Studio tools for Office runtime の概要](visual-studio-tools-for-office-runtime-overview.md)
- [Visual Studio &#40;での Office 開発の概要&#41;](getting-started-office-development-in-visual-studio.md)
- [Office 開発のサンプルとチュートリアル](office-development-samples-and-walkthroughs.md)
- [Office ソリューションの設計と作成](designing-and-creating-office-solutions.md)
